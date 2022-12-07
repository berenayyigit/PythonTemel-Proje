# PythonTemel-Proje
flatten and reverse functions

#helper funciton
def isNested(liste):
  check = False
  for i in liste:
    if type(i) == list:
            check = True
  return check

#flatten function
def flatten(liste):
  newList = []
  
  for i in liste:
    if (type(i) == list):
      for m in i:
        newList.append(m)
    else:
      newList.append(i)

  if isNested(newList):
    theList = flatten(newList)
    return theList
  else:
    return newList

#reverse function
def reverse(liste):
  liste = liste[::-1]
  
  if isNested(liste):
    for i in liste:
      index = liste.index(i)
      subList = reverse(i)
      liste[index] = subList
  
  return liste
