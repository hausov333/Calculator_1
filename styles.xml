package com.example.calculator

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import kotlinx.android.synthetic.main.activity_main.*
import net.objecthunter.exp4j.ExpressionBuilder
import java.lang.Exception

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        b_0.setOnClickListener{setTextFields("0")}
        b_1.setOnClickListener{setTextFields("1")}
        b_2.setOnClickListener{setTextFields("2")}
        b_3.setOnClickListener{setTextFields("3")}
        b_4.setOnClickListener{setTextFields("4")}
        b_5.setOnClickListener{setTextFields("5")}
        b_6.setOnClickListener{setTextFields("6")}
        b_7.setOnClickListener{setTextFields("7")}
        b_8.setOnClickListener{setTextFields("8")}
        b_9.setOnClickListener{setTextFields("9")}
        b_skl.setOnClickListener{setTextFields("(")}
        b_skr.setOnClickListener{setTextFields(")")}
        b_min.setOnClickListener{setTextFields("-")}
        b_sum.setOnClickListener{setTextFields("+")}
        b_umn.setOnClickListener{setTextFields("*")}
        b_div.setOnClickListener{setTextFields("/")}

        b_AC.setOnClickListener{
            math_operation.text=""
            result_text.text=""
        }

        b_back.setOnClickListener{
            val str = math_operation.text.toString()
            if (str.isNotEmpty()){ math_operation.text= str.substring(0,str.length-1) }
            result_text.text=""
        }

        b_ravn.setOnClickListener{
            try {
                val ex = ExpressionBuilder(math_operation.text.toString()).build()
                val result = ex.evaluate()
                val longRes =  result.toLong()
                if (result == longRes.toDouble())
                    result_text.text = longRes.toString()
                else
                    result_text.text = result.toString()

            }catch (e:Exception){
                Log.d("Ошибка", "сообщение: ${e.message}")
            }
        }
    }
    fun setTextFields(str: String){
        if (result_text.text!=""){
            math_operation.text = result_text.text
            result_text.text = ""
        }
        math_operation.append(str)
    }
}
