# #The code was done on google Colaboratory.

from numpy import *
!pip install numpy-stl       
 #Importing a library that is not in Colaboratory

from stl import mesh



#The following line of codes is used for uploading the given str file 

print("please upload the file ")                         
from google.colab import files
uploaded=files.upload()


#The following line of codes is used for Reading the given str file 

geometry_raw = mesh.Mesh.from_file('assignment.stl')


#plotting the given str file 

from mpl_toolkits import mplot3d
from matplotlib import pyplot
figure = pyplot.figure()
axes = mplot3d.Axes3D(figure)

axes.add_collection3d(mplot3d.art3d.Poly3DCollection(geometry_raw.vectors))

scale = geometry_raw.points.flatten()
axes.auto_scale_xyz(scale, scale, scale)

pyplot.show()
