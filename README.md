# miscellaneous_tools
Short snippets of R - code that users may find useful

This will be a collection of small possibly useful code that you can feel free to copy and utilize.


1. Select and copy wanted files.    
Say for instance, you have a large collection of files in an unrecognizable format (plate and cell numbers). You may have a reference file that has the sample names next to the plate name and cell numbers. Wouldn't it be nice to be able to make a csv list of files you want to copy over and have R copy it over for you?     

Line 1: What we want to do is create a path to the folder where where all the files are current.folder, then go create a folder to where you want to copy the files into (you can do this in file explorer).     
Line 2: Set the path of the new folder as new.folder.       
Line 3: Read in a csv file containing one column of the name of files you want to copy over into new folder.          
Line 4: Run the last line of code to copy files.        
```
current.folder <- "path_to_folder_to_copy_from"
new.folder <- "path_to_folder_to_copy_to"

files<-as.vector(read.csv("file_with_one_column_of_names.csv",header=F)$V1)

file.copy(paste0(current.folder,"/",files),new.folder)
```