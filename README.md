# StikSoft

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour {

	public float speed = 5f;
	public float jumpSpeed = 5f;
	private float movement = 0f;
	private Rigidbody2D rigidBody;
	public Transform groundCheckPoint;
	public float groundCheckRadius;
	public LayerMask groundLayer;
	private bool isTouchingGround;
	public Vector3 respawnPoint;

	// Use this for initialization
	void Start () {
		rigidBody = GetComponent<Rigidbody2D> ();
		respawnPoint = transform.position;
	}

	// Update is called once per frame
	void Update () {
		//to check if the ground check radius is touching the ground layer 
		isTouchingGround = Physics2D.OverlapCircle (groundCheckPoint.position, groundCheckRadius, groundLayer);
		movement = Input.GetAxis ("Horizontal");
		if (movement > 0f) {
			rigidBody.velocity = new Vector2 (movement * speed, rigidBody.velocity.y);
		}
		else if (movement < 0f) {
			rigidBody.velocity = new Vector2 (movement * speed, rigidBody.velocity.y);
		}

		if(Input.GetButtonDown ("Jump") && isTouchingGround) {
			rigidBody.velocity = new Vector2(rigidBody.velocity.x,jumpSpeed);
		}
	}

	void OnTriggerEnter2D(Collider2D other){
		if (other.tag == "FallDetector") {
			// what will happen when player enters the FallDetector zone
			transform.position = respawnPoint;
		}
		if (other.tag == "Checkpoint") {
			respawnPoint = other.transform.position;
		}
	}
}
