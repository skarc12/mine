// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Or.hdl

 /**
 * Or gate:
 * out = 1 if (a == 1 or b == 1)
 *       0 otherwise
 */

CHIP Or {
    IN a, b;
    OUT out;

    PARTS:
    Not(in=a, out=nota);
    Not(in=b,out=notb);
    Nand(a=nota, b=notb, out=out);
}




// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Not.hdl

/**
 * Not gate:
 * out = not in
 */

CHIP Not {
    IN in;
    OUT out;

    PARTS:
    Nand( a=in, b=in, out=out);
}


// // This file is part of www.nand2tetris.org
// // and the book "The Elements of Computing Systems"
// // by Nisan and Schocken, MIT Press.
// // File name: projects/01/And.hdl

// /**
//  * And gate: 
//  * out = 1 if (a == 1 and b == 1)
//  *       0 otherwise
//  */

// CHIP And {
//     IN a, b;
//     OUT out;

//     PARTS:
//     Nand(a=a, b=b, out=AnandB);
//     Not(in=AnandB, out=out);
// }


// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/And.hdl

/**
 * And gate: out = 1 if {a==1 and b==1}, 0 otherwise
 * And gate: if {a==1 and b==1} then out = 1 else out = 0
 */

CHIP And {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
   // Xor(a=a,b=b,out=out);
    Nand(a=a, b=b, out=c);
	Nand(a=c, b=c, out=out);
	   }
     
     
     // This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/And16.hdl

/**
 * 16-bit bitwise And:
 * for i = 0..15: out[i] = (a[i] and b[i])
 */

CHIP And16 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
    // Put your code here:

	Nand(a=a[0], b=b[0], out=c0);
	Nand(a=c0, b=c0, out=out[0]);

	Nand(a=a[1], b=b[1], out=c1);
	Nand(a=c1, b=c1, out=out[1]);

	Nand(a=a[2], b=b[2], out=c2);
	Nand(a=c2, b=c2, out=out[2]);

	Nand(a=a[3], b=b[3], out=c3);
	Nand(a=c3, b=c3, out=out[3]);

	Nand(a=a[4], b=b[4], out=c4);
	Nand(a=c4, b=c4, out=out[4]);

	Nand(a=a[5], b=b[5], out=c5);
	Nand(a=c5, b=c5, out=out[5]);

	Nand(a=a[6], b=b[6], out=c6);
	Nand(a=c6, b=c6, out=out[6]);

	Nand(a=a[7], b=b[7], out=c7);
	Nand(a=c7, b=c7, out=out[7]);

	Nand(a=a[8], b=b[8], out=c8);
	Nand(a=c8, b=c8, out=out[8]);

	Nand(a=a[9], b=b[9], out=c9);
	Nand(a=c9, b=c9, out=out[9]);

	Nand(a=a[10], b=b[10], out=c10);
	Nand(a=c10, b=c10, out=out[10]);

	Nand(a=a[11], b=b[11], out=c11);
	Nand(a=c11, b=c11, out=out[11]);

	Nand(a=a[12], b=b[12], out=c12);
	Nand(a=c12, b=c12, out=out[12]);

	Nand(a=a[13], b=b[13], out=c13);
	Nand(a=c13, b=c13, out=out[13]);

	Nand(a=a[14], b=b[14], out=c14);
	Nand(a=c14, b=c14, out=out[14]);

	Nand(a=a[15], b=b[15], out=c15);
	Nand(a=c15, b=c15, out=out[15]);

}
   
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Xor.hdl

/**
 * Exclusive-or gate:
 * out = not (a == b)
 */

CHIP Xor {
    IN a, b;
    OUT out;

    PARTS:
    Nand(a=a,b=b, out=nandab);
    Or(a=a, b=b, out=orab);
    And(a=nandab, b=orab, out=out);
}


// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Not16.hdl

/**
 * 16-bit Not:
 * for i=0..15: out[i] = not in[i]
 */

CHIP Not16 {
    IN in[16];
    OUT out[16];

    PARTS:
    // Put your code here:
    Not(in=in[0], out=out[0]);
    Not(in=in[1], out=out[1]);
    Not(in=in[2], out=out[2]);
    Not(in=in[3], out=out[3]);
    Not(in=in[4], out=out[4]);
    Not(in=in[5], out=out[5]);
    Not(in=in[6], out=out[6]);
    Not(in=in[7], out=out[7]);
    Not(in=in[8], out=out[8]);
    Not(in=in[9], out=out[9]);
    Not(in=in[10], out=out[10]);
    Not(in=in[11], out=out[11]);
    Not(in=in[12], out=out[12]);
    Not(in=in[13], out=out[13]);
    Not(in=in[14], out=out[14]);
    Not(in=in[15], out=out[15]);

}


// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Or8Way.hdl

/**
 * 8-way Or: 
 * out = (in[0] or in[1] or ... or in[7])
 */

CHIP Or8Way {
    IN in[8];
    OUT out;

    PARTS:
    Or(a=in[0], b=in[1], out=c1);
     Or(a=in[2], b=in[3], out=c2);
      Or(a=in[4], b=in[5], out=c3);
       Or(a=in[6], b=in[7], out=c4);

    Or(a=c1, b=c2, out=c5);
      Or(a=c3, b=c4, out=c6);

    Or(a=c5, b=c6, out=out);
}



// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Or16.hdl

/**
 * 16-bit bitwise Or:
 * for i = 0..15 out[i] = (a[i] or b[i])
 */

CHIP Or16 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
    Not16(in=a, out=nota);
    Not16(in=b, out=notb);
    And16(a=nota, b=notb, out=x );
    Not16(in=x, out=out);


}
