namespace Core
{
    
    public class ValidadorDeCpf
    {
       
        public bool Validar(string Cpf)
        {
            Cpf = Cpf.Replace(".", "").Replace("-", "");
            string tamanhoDoCpf = Cpf;

            if (tamanhoDoCpf.Length != 11)
            {
                return false;
            }

            int[] cpfFracionado = new int[11];
            int verificadorDigito1 = 0;
            for (int i = 0; i < 11; i++)
            {
                cpfFracionado[i] = int.Parse(tamanhoDoCpf[i].ToString());
            }

            if (cpfFracionado[0] + cpfFracionado[1] == cpfFracionado[2] + cpfFracionado[3])
            {
                return false;
            }

            for (int i = 0; i < 9; i++)
            {
                verificadorDigito1 += (10 - i) * cpfFracionado[i];
            }

            int resultadoDigito1 = verificadorDigito1 % 11;

            if (resultadoDigito1 == 1 || resultadoDigito1 == 0)
            {
                if (cpfFracionado[9] != 0)
                {
                    return false;
                }
            }
            else if (cpfFracionado[9] != 11 - resultadoDigito1)
            {

                return false;

            }

            int verificadorDigito2 = 0;
            for (int i = 0; i < 10; i++)
            {
                verificadorDigito2 += (11 - i) * cpfFracionado[i];
            }
            int resultadoDigito2 = verificadorDigito2 % 11;

            if (resultadoDigito2 == 1 || resultadoDigito2 == 0)
            {
                if (cpfFracionado[10] != 0)
                {
                    return false;
                }
            }
            else if (cpfFracionado[10] != 11 - resultadoDigito2)
            {

                return false;

            }
         
            return true;
        }
    }
}
