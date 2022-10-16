# leetCode_Palindrome

/*

Given an integer x, return true if x is palindrome integer.
An integer is a palindrome when it reads the same backward as forward.
For example, 121 is a palindrome while 123 is not.

 */

fun main(args: Array<String>) 
{
    var input = Solution()
    
    println(input.isPalindrome(75257))
}

class Solution{

    /*straight approach
    
    fun isPalindrome(x : Int) : Boolean{
        if(x < 0){
            return false
        }
        var y = x.toString().reversed()
        return x == y.toInt()
    }
    */
    
    fun isPalindrome(x : Int) : Boolean{
        if(x < 0){
            return false
        }
        val digitList = mutableListOf<Int>()
        var number = x
        while (number > 0){
            digitList.add(number % 10)
            number /= 10
        }
        var left = 0
        var right = digitList.size-1
        while (left < right){
            if(digitList[left] != digitList[right]) {
                return false
            }
            left++
            right--
        }
        return true
    }
}
