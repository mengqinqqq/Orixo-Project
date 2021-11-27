#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Fri Nov 26 01:52:50 2021

@author: xihongshijidanzhajiangmian
"""

#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Mon Nov 15 23:12:19 2021

@author: xihongshijidanzhajiangmian
"""


def read_bff(filename):
    '''
    Read the bff file

    **Parameters**

        filename: *str*
            a .bff file
        number_of_block:*int*
            how many blocks in the file

    **Return**
        box: *list*
        a list contains all the seperated blocks
            
    '''
    
    file = open(filename, 'r').read()
    line_split = file.split('\n')
    # split the input file by line

    find_start=line_split.index('GRID START')
    find_stop=line_split.index('GRID STOP')
    new_file=line_split[find_start+1:find_stop]
#find the start and stop position and then split them
    number_of_block=new_file.count('')+1
   
    box=[]
    if number_of_block==1:
        return (new_file)
    else:
        if number_of_block==2:
            
            index_one=new_file.index('')
            first_split=new_file[0:index_one]
            second_split=new_file[index_one+1:]
            a=(first_split,second_split)
            box=[a[0],a[1]]
            
            return box
    
        if number_of_block==3:
            index_one=new_file.index('')
            first_split=new_file[0:index_one]
            new_file.pop(index_one)
            index_two=new_file.index('')
            second_split=new_file[index_one:index_two]
            third_split=new_file[index_two+1:]
            return box.append(first_split,second_split,third_split)
 #seperate all the blocks by finding all the empty positions  


def count_cols():
    '''
    find how many cols in each block
    the number of cols is same in every block
    
    ***parameters***
        a:*str*
            the first row in the first block
    

    ***Returns***
        num_cols: *int*
            how many columns in the first block (same as other blocks)
    
    '''

    block=read_bff('board_1_50.bff')
 
    first_row=block[0][0]
#the first row in block 1
    a=''.join(first_row.split())
    num_cols=len(a)
    return num_cols

def count_rows():
    '''
    find how many rows in each block
    the number of rows is same in every block
    
    ***parameters***
        a:*str*
            the first row in the first block
    

    ***Returns***
        num_rows: *int*
            how many rows in the first block (same as other blocks)
    
    '''
    
    block=read_bff(filename)
    
    num_rows=len(block[0])
    return num_rows



def solve_problem(filename):
    '''

    '''
    def solu():
        '''
        Write the each step of solution in the file
        the format is: coordination + direction.

        '''
        f = open(file)
        for i in solu:
            f.write(str(i[0]) + ',' + str(i[1][0]) + '\n')

    file = filename[:-4] + '_solution.txt'
    # create the filename
    
    f = open(file)
    f.write('solution:')
    boxlist = read_bff(filename)
    # read the bff and convert them to lists

    # solve the boxes and write all the steps in a text file.
    if len(boxlist) == 1:
        f.write('\nbox1:\n')
        write_solu(solve(boxlist[0]))

    elif len(boxlist) == 2:

        f.write('\nbox1:\n')
        write_solu(solve(boxlist[0]))
        f.write('\nbox2:\n')
        write_solu(solve(boxlist[1]))

    elif len(boxlist) == 3:

        f.write('\nbox1:\n')
        write_solu(solve(boxlist[0]))
        f.write('\nbox2:\n')
        write_solu(solve(boxlist[1]))
        f.write('\nbox3:\n')
        write_solu(solve(boxlist[2]))


    f.write('instructions:\n')
    f.write('[,]represents the coordinate of grid while N W S E represents north west south and east seperatly\n')
    f.write('the coordinate starts from zero\n')


    f.close()


class Block():
    '''
    
    this class is used to define organize the coordination of each grid
    and the way for moving
    

    '''
    box=read_bff(filename)
    
    def __init__(self, x, y, z, box):
        '''
        **Parameters**

            x: *int*
                define which block we are dealing with
            y: *int*
                define which row
            z: *int*
                define which column
        '''
        self.x = x
        self.y = y
        self.z = z
        self.box=box

    def num(self):
        '''
        this function is used to define a specific number
        written as [x,y,z]
        
        **Return**
            num: *int*
                the specific number with a coordinate [x,y,z]
        '''
        box=read_bff(filename)
        a=box[self.x][self.y]
        b=''.join(a.split())
        #the specific row in box
        return b[self.z]

    def coor(self):
        '''
        this function is used to define coordinate
        
        **Return**
            coor: *list*
                coordinate of the specific grid
        '''
        return [self.x,self.y,self.z]
    
    
    def option(self):
        '''
        this function is used to define the direction of a specific coordinate
        and the number of o in the cooresponding direction
        the possible ways of moving can be obtain by this function
        
        ***parameters***
        nW, nE, nN, nS:*int*
            the number of o in corresponding direction
        W, E, N, S:*str*
            direction of o
        **Return**
            option: *list*
                coordination of this box.
        Find all the moving options around the box. Count how many grids are
        available to move in each direction.

        '''
        output = []
        box=read_bff('board_1_50.bff')
        a=box[self.x][self.y]
        b=''.join(a.split())
        c=b[self.z]
        #define the coordinate

        d=count_cols()
        e=count_rows()
        ro=count_rows()
        co=count_cols()
        #count how many rows and columns in the block

        
        x, y, z = self.x, self.y, self.z
        nW, nE, nN, nS = 0, 0, 0, 0
#define the initial values

        x0, y0, z0 = x, y, z
        for y0 in range(len(d)):
            for x0 in range(len(number_of_block)):
                for z0 in range (len(e)):
                    while y0>=0:
                        if box[x0][y0][z0]=='o':
                            nW=nW+1
                        y0=y0-1
                    while y0 <= co - 1:

                        if box[x0][y0][z0]=='o':
                            nE += 1
                        x0 += 1
                    while z0>=0:
                        if box[x0][y0][z0]=='o':
                            nN=nN+1
                        z0=z0-1
                    while z0<=ro-1:
                        if box[x0][y0][z0]=='o':
                            nS=nS+1
                        z0=z0+1
                        
#calculate the number of o in four different direction (N W S E) by iteration and substitution 
#if the number of o is both larger than the specific value of grid and not equal to zero,
#a possible way to move the grid comes up

        if nW != 0 and nW >= c:
            output.append(['W', nW])
        if nE != 0 and nE >= c:
            output.append(['E', nE])
        if nN != 0 and nN >= c:
            output.append(['N', nN])
        if nS != 0 and nS >= c:
            output.append(['S', nS])
        return output
              
            
def first():
    '''
    first happens when there is only one direction to move 
    and the number of 'o' is equal to the grid value,

    **Parameters**


    **Return**

        first_list: *list*
            a list contains the first move, including a coordinate and a direction

    '''
    first_list = []
    a=count_cols()
    b=count_rows()
    
    
    for i in range(len(a)):
        for j in range(len(b)):
            for k in range(len(number_of_block))
            point=Block(k,i,j,box)
            if len(point.option())==1 and point.option()[0][1]==box[k][i][j]:
                move_list.append([point.coor()[1][2], point.option()[0]])
    return first_list
#find the first move we considered by 
#th only one direction get in class and option function
#the same amount of o and grid



def second():
    '''
    define a list that contains all possible moves

    **Parameters**


    **Return**
        second_list: *list*
           a list contains all the possible move that a grid can go
           a list including a coordinate and a direction
    '''
    second_list = []
    a=count_cols()
    b=count_rows()
    
    
    for i in range(len(a)):
        for j in range(len(b)):
            for k in range(len(number_of_block))
            point=Block(k,i,j,box)
            for m in point.option():
                second_list.append([point.coor()[1][2], point.option()[0]])
    return second_list
#find all possible ways to move the grid by
#collecting the direction and the coordinate of all the possible move



def solve():
    '''
    
    This function is a solver
    it can solve the problem by move the result from first function
    and then move the result from the second function
    this function is not completed by the my limited ability

    **Parameters**

        box: *list*
            list of box to be solved.

    **Return**

        record3: *list*
            Record the list of move(solution).

    '''
    box= []
    block=read_bff(filename)

    first = must_move(block)
    return box


    
    
if __name__ == '__main__':

    solve_problem('board_1_02.bff')
    solve_problem('board_1_03.bff')
    solve_problem('board_1_13.bff')
    solve_problem('board_1_14.bff')
    solve_problem('board_1_50.bff')
    solve_problem('board_2_02.bff')
    solve_problem('board_2_16.bff')
    solve_problem('board_3_14.bff')
    solve_problem('board_4_26.bff')
    
    
#this solution also need a delete of all the moved o and values between every move
#however this is not finished before deadline due to peosonal limited skills

