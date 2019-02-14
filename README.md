using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Producto
{
    class Datos
    {
        public string articulo;

        public string Articulo
        {
            get { return articulo; }
            set { articulo = value; }
        }


        public Datos()
        {
            articulo = "";       
        }

        public Datos(string art)
        {
            articulo = art;
        }



        #region //Unidad del producto y Desplegar Cantidad
        //Unidad del producto
        int[] unidadCosto = new int[3];

        public void Cantidad()
        {
            int x = 25;
            for (int o = 1; o < unidadCosto.Length; o++)
            {             
                int y = 1;
                //Cantidad de articulos
                Console.ForegroundColor = ConsoleColor.DarkYellow;
                Console.SetCursorPosition(x, 1 + o);
                Console.Write(" - Cantidad del articulo: ");
                Console.ForegroundColor = ConsoleColor.White;
                Console.SetCursorPosition(51, y + o);
                unidadCosto[o] = int.Parse(Console.ReadLine());
            }
     
        }

        public void DesplegarCantidad()
        {
            for (int o = 1; o < unidadCosto.Length; o++)
            {
                
                Console.ForegroundColor = ConsoleColor.White;
                Console.SetCursorPosition(30, 4 + o);

                Console.Write(unidadCosto[o]);
                
            }
        }

        public void FactorDeCostos()
        {
            Random rnd = new Random();
            int numero;
            numero = rnd.Next(5, 16);

            for (int o = 1; o < unidadCosto.Length; o++)
            {

                Console.ForegroundColor = ConsoleColor.White;
                Console.SetCursorPosition(58, 4 + o);
                Console.Write((unidadCosto[o] * (numero/100)));
            }
        }


        //Total de unidad producidas
        public void totales()
        {
           int acumulador = 0;
           for(int o = 1; o < unidadCosto.Length; o++)
            {  
                acumulador = acumulador + unidadCosto[o];
            }
            Console.SetCursorPosition(30, 8);
            Console.Write(acumulador);
        }

        #endregion 

        #region //Costo de los Articulos
        int[] costoFijo = new int[3];

        public void CostoArticulo()
        {
            int xx = 63;
            for (int ca = 1; ca < costoFijo.Length; ca++)
            {
                int yy = 1;
                //Costo de los articulos
                Console.ForegroundColor = ConsoleColor.DarkYellow;
                Console.SetCursorPosition(xx,1 + ca);
                Console.Write(" - Costo del articulo: ");
                Console.ForegroundColor = ConsoleColor.White;
                Console.SetCursorPosition(86, yy + ca);
                costoFijo[ca] = int.Parse(Console.ReadLine());
            }
        }

        public void DesplegarArticulo()
        {
            for(int ca = 1; ca < costoFijo.Length; ca++)
            {
                Console.SetCursorPosition(82, 4 + ca);
                Console.Write(costoFijo[ca]);
            }
        }

        #endregion

    }
}
