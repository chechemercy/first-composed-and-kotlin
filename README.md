# first-composed-and-kotlin
 first application using composed and kotlin
package com.britney.britneyfirstapp

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.*
import androidx.compose.material.MaterialTheme
import androidx.compose.material.Surface
import androidx.compose.material.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.tooling.preview.Preview
import com.britney.britneyfirstapp.ui.theme.BritneyFirstAppTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            BritneyFirstAppTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colors.background
                ) {

                  britneyWithImage("britney",message="happy birthday princess",from="britney")
                }
            }
        }
    }
}

@Composable
fun britneyWithImage(name: String, message:String,from:String) {
    val image = painterResource(id=R.drawable.androidparty)
Box() {
    Image(painter = image, contentDescription =null)


    Row() {
        Text(text=name)
        Text(text="")


        Column() {
            Text(text=name)
            Text(text="")
            Text(text="")
        }
    }


}
}

@Preview(showBackground = true,name="Happy Birthday Princess",showSystemUi=true)
@Composable
fun britneyPreview() {

        britneyWithImage(name = "britney", message ="Happy Birthday Princess",from ="britney")
    }
