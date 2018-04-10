# StikSoft
//Shows just text

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ShowText : MonoBehaviour {

	// Use this for initialization
	void Start () {
		
	}
	
	// Update is called once per frame
	void Update () {
		
	}
	//type text inbetween " " 
	//x1, y1 is the top left x2,y2 is the bottom right
	// 
	void OnGUI(){
		GUI.Label(new Rect (x1, y1, x2, y2), "Yeet");
	}
}

