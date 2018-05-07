# StikSoft

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class LevelManager : MonoBehaviour {
	public float respawnDelay;
	public PlayerController gamePlayer;
	public int coins;
	public Text coinText;
	public int score = 0;
	 
	// Use this for initialization
	void Start () {
		gamePlayer = FindObjectOfType<PlayerController> ();
		coinText.text = "Score: " + coins;
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
		coins += numberOfCoins;
		coinText.text = "Score: " + coins;
	}
}
