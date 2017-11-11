# Cube-and-Cylinder
#include <iostream>
#include <fstream>
#include <vector>
using namespace std;

class Shape {
public:
};

class Cylinder : public Shape{
private:
    double r, h;
    int facets;
public:
    Cylinder(double x, double y, double z, double r, double h, int facets) {}
};

class Cube: public Shape {
private:
    double size;
public:
    Cube(double x, double y, double z, double size) : size(size) {}
};

class CAD {
private:
    vector<Shape*> shapes;
    int n;
public:
    CAD()
    {
        n=0;
    }
    ~CAD()
    {
        for(int i=0;i<n;i++)
            delete shapes[i];
    }
    void add()
    {
        shapes[n++] = new Cube(0,0,0, 5);
        shapes[n++]= new Cylinder(100,0,0, 3,10,10);
    }
    void write()
    {
        vector<Shape*> shpes,const char "test.stl[]";
    }
};

//https://www.stratasysdirect.com/resources/how-to-prepare-stl-files/
//https://www.viewstl.com/
int main() {
    CAD c;
    c.add(new Cube(0,0,0,   5));
    c.add(new Cylinder(100,0,0,    3, 10, 10));
    c.write("test.stl");
}
