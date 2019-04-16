# efsoltor
Комментарии отсутствуют
Сложение
public static string Plus(string array)
        {
            string text = array;
            string one = "", two = "";
            int i = 0;
           
            
            for ( i = 0; i < text.Length; i++)
            {
                if (text[i] == '+')
                {
                    break;
                }
                one += text[i];

            }
            for (i=i+1; i < text.Length; i++)
            {
                two += text[i];
            }

            string plus = one + "\n" + two + "\n";
            plus += "__________" + "\n";

            char[] no = one.ToCharArray();
            char[] nt = two.ToCharArray();
            int e = 0, vc = 0, lc = 0;
            string right = "";
            if (one.Length < two.Length)
            {
                vc = two.Length - 1;
                lc = one.Length - 1;

                for (int j = vc; j >= 0; j--)
                {
                    for (e = lc; e >= 0; e--)
                    {

                        int zn = (int)Char.GetNumericValue(no[e]) + (int)Char.GetNumericValue(nt[j]);
                        plus += zn.ToString() + right;
                        plus += "\n" ;
                        right += "_";
                        j--;
                        if (e == 0 )
                        {
                            break;
                        }
                    }
                    if (e == 0)
                    {
                        break;
                    }
                }
            }
            else
            {
                lc = two.Length - 1;
                vc = one.Length - 1;

                for (int j = vc; j >= 0; j--)
                {
                    for (e = lc; e >= 0; e--)
                    {

                        int zn = (int)Char.GetNumericValue(no[j]) + (int)Char.GetNumericValue(nt[e]);
                        plus += zn.ToString() + right;
                        plus += "\n";
                        right += "_";
                        j--;
                        if (e == 0 )
                        {
                            break;
                        }
                    }
                    if (e == 0)
                    {
                        break;
                    }
                }
            }
            
            plus += "__________" + "\n";
            plus += (Convert.ToDouble(one) + Convert.ToDouble(two)).ToString();
            return plus.ToString();
        }
 
Умножение
public static string Multiplication(string array)
        {
            string text = array;
            string one = "", two = "";
            int i = 0;


            for (i = 0; i < text.Length; i++)
            {
                if (text[i] == '*')
                {
                    break;
                }
                one += text[i];

            }
            for (i = i + 1; i < text.Length; i++)
            {
                two += text[i];
            }

            string plus = one + "\n" + two + "\n";
            plus += "__________" + "\n";

            char[] no = one.ToCharArray();
            char[] nt = two.ToCharArray();
            int e = 0, vc = 0, lc = 0;
            string right = "";
          
                vc = two.Length - 1;
                lc = one.Length - 1;
                int k = lc + 1;
            for (int j = vc; j >= 0; j--)
            {
                for (e = lc; e >= 0; e--)
                {

                    int zn = (int)Char.GetNumericValue(no[e]) * (int)Char.GetNumericValue(nt[j]);
                    plus += zn.ToString() + right;
                    plus += "\n";
                    right += "_";

                    if ( j != vc)
                    {
                        
                        plus = plus.Remove(plus.Length - k);
                        plus += "\n";  
                    }
                    
                }
            }
            

            plus += "__________" + "\n";
            plus += (Convert.ToDouble(one) * Convert.ToDouble(two)).ToString();
            return plus.ToString();
        }
 

























Вычитание
public static string Minus(string array)
        {
            string text = array;
            string one = "", two = "";
            int i = 0;


            for (i = 0; i < text.Length; i++)
            {
                if (text[i] == '-')
                {
                    break;
                }
                one += text[i];

            }
            for (i = i + 1; i < text.Length; i++)
            {
                two += text[i];
            }

            string plus = one + "\n" + two + "\n";
            plus += "__________" + "\n";

            char[] no = one.ToCharArray();
            char[] nt = two.ToCharArray();
            int e = 0, vc = 0, lc = 0;
            string right = "";
            
                vc = two.Length-1;
                lc = one.Length-1 ;

                for (int j = lc; j >= 0; j--)
                {
                for (e = vc; e >= 0; e--)
                {

                    if (Convert.ToDouble(one) > Convert.ToDouble(two))
                    {
                        int zn = (int)Char.GetNumericValue(no[j]) - (int)Char.GetNumericValue(nt[e]);
                        if (zn < 0)
                        {
                            zn = (int)Char.GetNumericValue(no[j]) + 10 - (int)Char.GetNumericValue(nt[e]);
                            if (j > 0)
                            {
                                no[j - 1] = (char)((int)Char.GetNumericValue(no[j]) - 1);
                            }
                        }
                        plus += zn.ToString() + right;
                        plus += "\n";
                        right += "_";
                        j--;

                    }
                    else
                    {
                        int zn = (int)Char.GetNumericValue(nt[e]) - (int)Char.GetNumericValue(no[j]);
                        if (zn < 0)
                        {
                            zn = (int)Char.GetNumericValue(nt[e]) + 10 - (int)Char.GetNumericValue(no[j]);
                            if (j > 0)
                            {
                                no[j- 1] = (char)((int)Char.GetNumericValue(nt[e]) - 1);
                            }
                        }
                        plus += zn.ToString() + right;
                        plus += "\n";
                        right += "_";
                        j--;
                    }
                }
                }
            

            plus += "__________" + "\n";
            plus += (Convert.ToDouble(one) - Convert.ToDouble(two)).ToString();
            return plus.ToString();
        }
 




Деление
public static string Division(string array)
        {
            string text = array;
            string one = "", two = "";
            int i = 0;


            for (i = 0; i < text.Length; i++)
            {
                if (text[i] == '/'|| text[i] == ':')
                {
                    break;
                }
                one += text[i];

            }
            for (i = i + 1; i < text.Length; i++)
            {
                two += text[i];
            }

            string plus = one + " |   " + two + "\n";
            plus += "------------" + "\n";
           

            double result = Convert.ToDouble(one) / Convert.ToDouble(two);
            result = Math.Round(result, 2);

            plus += " |" + Math.Round(result, 2).ToString() + "\n"+ "_____" + "\n";
            

            char[] nt = two.ToCharArray();
            char[] re = ((result).ToString()).ToCharArray();

            int e = 0, lc = 0, h=0;
            

            lc = re.Length;
            string s = ".";
            int p = result.ToString().IndexOf(s);
            string fin = result.ToString().Remove(0, p + s.Length);
            

            char[] fi = fin.ToCharArray();
            for (e = 0; e < lc; e++)
                {

                    if (re[e] == '.')
                {
                    continue;
                }

                int zn = Convert.ToInt32(two) * (int)Char.GetNumericValue(re[e]);
                    
                if (e == 0)
                {
                    plus += "-" + Math.Floor(result) * Convert.ToInt32(two);

                    plus += "\n"+ "=" + (Convert.ToInt32(one) - Convert.ToInt32(Math.Floor(result) * Convert.ToInt32(two))).ToString();

                    plus += "\n" + "--------";
                    if ((Convert.ToInt32(one) - Convert.ToInt32(Math.Floor(result) * Convert.ToInt32(two))) != 0)
                    {
                        h = (Convert.ToInt32(one) - (Convert.ToInt32(Math.Floor(result) * Convert.ToInt32(two))))*10;
                       plus += "\n" + "=" + (Convert.ToInt32(one) - Convert.ToInt32(Math.Floor(result) * Convert.ToInt32(two))).ToString() + "0";
                       
                    }
                }
                
                else
                {
                 for(int k=0; k < fin.Length; k++)
                    {
                        plus += "-"+ (int)Char.GetNumericValue(fi[k]) * Convert.ToInt32(two)+"\n";
                        plus += "--------"+"\n";
                        if (k==1)
                        {
                           break;
                        }

                       plus += "=" + (h - ((int)Char.GetNumericValue(fi[k]) * Convert.ToInt32(two)))*10 + "\n";
                       h=(h - ((int)Char.GetNumericValue(fi[k]) * Convert.ToInt32(two) * 10))-((int)Char.GetNumericValue(fi[k]) * Convert.ToInt32(two));

                    }
                    break;
                }

                   // plus = plus.Remove(plus.Length - (zn.ToString()).Length);
                    plus += "\n";

            }

            
            return plus.ToString();
        }







 
