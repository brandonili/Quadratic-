# Quadratic-
Creating a quadratic formula 

public class Quadratic {

    // attributes
    private double a;
    private double b;
    private double c;

    // default constructor to initialize the coefficients to 0
    public Quadratic() {
        a = 0;
        b = 0;
        c = 0;
    }

    // method to set the coefficients to specified values
    public void set(double a, double b, double c) {
        this.a = a;
        this.b = b;
        this.c = c;
    }

    // accessors
    // return value of a
    public double getA() {
        return a;
    }

    // return value of b
    public double getB() {
        return b;
    }

    // return value of c
    public double getC() {
        return c;
    }

    // method to evaluate the quadratic equation at x and return the evaluated value
    public double evaluate(double x) {
        return a * Math.pow(x, 2) + b * x + c;
    }

    // method to return a copy of this object
    public Quadratic clone() throws CloneNotSupportedException {
        // create a new object
        Quadratic q = new Quadratic();
        q.set(a, b, c); // set the values to values of this object
        return q;
    }

    // method to return true if obj is an object of Quadratic and coefficients of this and obj are equal
    public boolean equals(Object obj) {
        if (obj instanceof Quadratic) // obj is an object of Quadratic
        {
            Quadratic q = (Quadratic) obj; // cast to Quadratic

            return a == q.a && b == q.b && c == q.c;
        }

        return false; // not an object of Quadratic
    }

    // return String representation of Quadratic
    public String toString() {
        return (this.a + "*x^2 + " + this.b + "x + " + this.c);
    }
    
    
    // method to return a Quadratic object obtained by adding q1 and q2 i.e each coefficients of q1 and q2 are added to get the resultant object
    public Quadratic sum(Quadratic x1, Quadratic x2) {
        Quadratic result = new Quadratic();
       double x,y,z;
   
       x=x1.a + x2.a;
    
       y=x1.b + x2.b;
       
       z=x1.c + x2.c;
        
       result.set(x,y,z);

        return result;
    }

    // method to return a Quadratic object obtained by multiplying q qith r i.e each coefficients of q are multiplied by r
    public Quadratic scale(double r, Quadratic q) {
        Quadratic result = null;
        result.set(q.a * r, q.b * r, q.c * r);
        return result;
    }
    public static void main(String args[]) {
        
        Quadratic q1 =  new Quadratic ();
        q1.set(1, 2, 3);
       
        Quadratic q2 =  new Quadratic ();
        q2.set(1, 1, 1);
        
        Quadratic total = new Quadratic ();
      
        total.sum(q1, q2);
        
        
        System.out.println("result is:  "+total.sum(q1, q2));
        
    }
    
}
