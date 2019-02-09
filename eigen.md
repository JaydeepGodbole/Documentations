#### Eigen

##### Compiling and running your codes in c++ eigen*

BASIC USAGE : For using eigen library in your code.
# include <eigen3/Eigen/Dense>
using namespace Eigen;

Compile the code using **g++ code.cpp**

##### The matrix class

* All matrices and vectors are objects of the **Matrix** template class.

* The three mandatory template parameters of Matrix are:
**Matrix<typename Scalar, int RowsAtCompileTime, int ColsAtCompileTime>**

eg - typedef Matrix<float, 4, 4> Matrix4f;

* typedef Matrix<int, Dynamic, 1> VectorXi;  // Use dynamic if the number of rows and/or columns is not known at compile time.

* Constructors - A default constructor is always available, never performs any dynamic memory allocation, and never initializes the matrix coefficients. 

eg - Matrix3f a;
	 MatrixXf a(10,15);
	 VectorXf b(30);

* Coefficient accessors - a(3,3)

* Comma - initialization: 

eg - 
Matrix3f m;
m << 1, 2, 3,
     4, 5, 6,
     7, 8, 9;
std::cout << m;

* Resizing - The current size of a matrix can be retrieved by rows(), cols() and size(). These methods return the number of rows, the number of columns and the number of coefficients, respectively. Resizing a dynamic-size matrix is done by the resize() method.

The resize() method is a no-operation if the actual matrix size doesn't change; otherwise it is destructive: the values of the coefficients may change. If you want a conservative variant of resize() which does not change the coefficients, use conservativeResize()

* Assignment and resizing - Assignment is the action of copying a matrix into another, using operator=. Eigen resizes the matrix on the left-hand side automatically so that it matches the size of the matrix on the right-hand size.

* 