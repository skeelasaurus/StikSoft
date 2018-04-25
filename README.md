using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Dialogue : MonoBehaviour {

	
    

    public void OnGUI()
    {
        string[] choice = { "yeet", "skeet", "noodle" };
        GUI.Label(new Rect(100, 100, 100, 100), choice[1]);
    }




    // Use this for initialization
    void Start () {
		
	}
	
	// Update is called once per frame
	void Update () {
		
	}
}
