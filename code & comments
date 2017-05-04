import java.util.*;
import java.io.*;
import java.math.*;


class Solution {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);
        int L = in.nextInt();
        int H = in.nextInt();
        if (in.hasNextLine()) {
            in.nextLine();
        }
        String T = in.nextLine().toUpperCase();
        
        /*Two dimensional array to store the parts of String size L*26. 
        The reason for 26 is that there are 26 letters in the alphabet.
        and each letter is width L*/
        String[][] array = new String[H][26*L];
        
        for (int i = 0; i < H; i++) {
            String ROW = in.nextLine();
            for(int j = 0; j < 27; j++){
                /*Stored the pieces of string in the array using the substring method
                and using the Math formula of ((j+1) * L) - (L), (((j+1) * L) - (L)) + L
                As an example if j is 3 and L is 4: It would cover from elemnent
                16 to element 20 in the String. Once this is figured out, the rest is a
                matter of syntax.*/
                array[i][j] = ROW.substring(((j+1) * L) - (L), (((j+1) * L) - (L)) + L);
            }
        }
        
        //An array of letters in alphabetical order to use their positioning as reference.
        String letters = "A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z";
        //Get each letter into an array for easier indexing
        String[] indexArr = letters.split(",");
        
        
        char c = ' ';
        for(int i  = 0; i < H; i++){
            
            //empty String for output
            String output = "";
            
            /*These nested loops iterate through the original String (T) to find the 
            next letter to look for in the indexArr array, and see where in the array array
            we need to partition*/
            for(int j = 0; j < T.length(); j++){
                int index = -1; //int return the index in which the letter is in indexArr
                c = T.charAt(j);
                String temp = Character.toString(c);
                for(int z = 0; z < indexArr.length; z++){
                    if(temp.equals(indexArr[z])){
                        index = z;
                    }
                }
                /*This condition states that if the index is -1 then get the last element
                on the array array, which is the ? ASCII art. Else, get the element i from 
                array arrray*/
                if(index == - 1){
                        output += array[i][26];
                    }
                else{
                    output += array[i][index];
                }
                
            }
            System.out.println(output);
        }
        
    }
}
