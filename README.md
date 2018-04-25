# StikSoft

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class LevelManager : MonoBehaviour {
	public float respawnDelay;
	public PlayerController gamePlayer;
	public int coins;
	 
	// Use this for initialization
	void Start () {
		gamePlayer = FindObjectOfType<PlayerController> ();

	}
	
	// Update is called once per frame
	void Update () {
		
	} 

	public void Respawn() {
		gamePlayer.gameObject.SetActive (false);
		gamePlayer.transform.position = gamePlayer.respawnPoint;
		gamePlayer.gameObject.SetActive (true);
	}

	public void AddCoins(int numberOfCoins){
		
	}
}
