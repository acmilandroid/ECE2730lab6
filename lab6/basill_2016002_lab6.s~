# Basil Lin
# Section 002
# Lab 6
# Purpose - create Factorial calculation program by using recursion.
#			Learn to create recursive functions in assembly.

.globl Factorial
.type Factorial, @function
Factorial:
	/* prolog */
	pushl %ebp			#writes to stack
	pushl %ebx			#writes to stack
	movl %esp, %ebp
	subl $4, %esp

	/* put code here */
	movl 12(%ebp), %ecx	#moves n to register %ecx
	cmp $0, %ecx		#if(n == 0)
	je return1
	cmp $1, %ecx		#if(n == 1)
	je return1
	jmp else
return1: 				#function to return 1
	movl $1, %eax
	jmp end
else:					#function to return n * Factorial(n-1)
	movl %ecx, -4(%ebp)	
	subl $1, %ecx		#decrements n
	addl %ecx, %ebx
	pushl %ecx			#writes to stack
	call Factorial		#recursion; calls Factorial function again
	movl -4(%ebp), %ecx	#moves n to %ecx
	mull %ecx			#n * Factorial(n-1)
	jmp end
end:
	/* epilog */
	movl %ebp, %esp
	popl %ebx			#copies stack
	popl %ebp
	ret

