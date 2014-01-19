# Simple Iterations classes C#
====================

This is C# simple realisation of Seidel and Jacobi methods.  

There are two classes Seidel and Jacobi are innerhited from base abstract class SimpleIterations.

## Usage


...csharp
// 1. Create a square two-dimensional matrix of coefficients.

double[,] matrix = new double[3, 3] {
  { 4, 0.24, -0.08}, 
  { 0.09, 3, -0.15}, 
  { 0.04, -0.08, 4}
};
// Create an additional one-dimentional array of free coefficients

double[] additional = new double[3] {
  8, 
  9, 
  20
};

// Create an instance of selected class 
// You have to init it with constructor 
// args are - matrix coefficients, matrix of additional, accuracy
Seidel i = new Seidel(matrix, additional, 0.0001);
Jacobi j = new Jacobi(matrix, additional, 0.0001);

// Then call calcualte method of class to calculate answers

i.calculateMatrix();
j.calculateMatrix();

// to get results you have to get it from field called ClassName.ResultMatrix
// it will return one-dimentional array with answers.

Console.WriteLine("\n Seidel method:");
showMatrix(i.ResultMatrix);
Console.WriteLine("\n Jakobi method:");
showMatrix(j.ResultMatrix);

...

## License

MIT 