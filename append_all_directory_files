import sys
import os
import codecs

original_directory = "C:/Users/drummond/Documents/DCCC/data/PDI/DCCC"

state_total = []

os.chdir(original_directory)
allfiles = os.listdir(original_directory)
for filename in allfiles:
    filenamelength = filename.find('.')
    district = filename[:filenamelength]
    district = district[0:2]+"-"+district[2:4]
    with open(filename, "r") as current_file:
        read_file = current_file.read()
    current_file.closed
    lines = read_file.split("\n")
    lines = lines[7:]
    for line in lines:
        if district != "DC-CC":
            line = district+"\t"+line
            state_total.append(line)

row = "District\tField\tVoters\tPercentVoters\tNT_houses\tPercentNT_houses\n"
with open("PDI_State.txt", 'a') as myfile:
    myfile.write(row)
for line in state_total:
    line=line+"\n"
    with open("PDI_State.txt", 'a') as myfile:
        myfile.write(line)
