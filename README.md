# gabaritoProvaCsharp
Um sistema simples que serve como gabarito para correção de provas.



using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        
        Console.WriteLine("Informe o gabarito (3 respostas) ");
        List<string> gabarito = new List<string>();
        for (int x = 0; x < 3; x++)
        {
            Console.Write("Informe a resposta da pergunta " + (x + 1) + "\n");
            gabarito.Add(Console.ReadLine());
        }

        
        Console.Write("Informe quantos alunos: ");
        int quantos = int.Parse(Console.ReadLine());

        
        List<List<string>> respostas = new List<List<string>>();
        for (int candi = 0; candi < quantos; candi++)
        {
            List<string> respostaAluno = new List<string>();
            for (int resp = 0; resp < 3; resp++)
            {
                Console.Write("Candidato " + (candi + 1) + ": resposta " + (resp + 1) + "\n");
                respostaAluno.Add(Console.ReadLine());
            }
            respostas.Add(respostaAluno);
        }

        
        Console.WriteLine();
        int cont = 0;
        foreach (var i in respostas)
        {
            cont++;
            Console.WriteLine("Candidato " + cont);
            Console.WriteLine("Respostas: " + string.Join(", ", i));
            int acertos = 0;
            for (int x = 0; x < 3; x++)
            {
                if (gabarito[x] == i[x])
                {
                    acertos++;
                }
            }
            Console.WriteLine("Acertou: " + acertos);
        }
    }
}
