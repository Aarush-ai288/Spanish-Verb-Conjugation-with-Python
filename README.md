# Spanish-Verb-Conjugation-with-Python
This code takes a Spanish verb and pronoun as input and returns the appropriately conjugated verb.
def conjug(pronoun, word):
    stem = word[:-2].lower()
    end = word[-2:].lower()
    pro = pronoun.lower()
    newWord = ""

    if pro == "yo":
        ending = end.replace(end, "o")
        newWord = pro + " " + stem + ending
    elif pro == "tu":
        if end == "er" or end == "ir":
            ending = end.replace(end, "es")
            newWord = pro + " " + stem + ending
        elif end == "ar":
            ending = end.replace(end, "as")
            newWord = pro + " " + stem + ending
    elif pro == "nosotros":
        if end == "ar":
            ending = end.replace(end, "amos")
            newWord = pro + " " + stem + ending
        elif end == "er":
            ending = end.replace(end, "emos")
            newWord = pro + " " + stem + ending
        elif end == "ir":
            ending = end.replace(end, "imos")
            newWord = pro + " " + stem + ending
    elif pro == "el" or pro == "ella" or pro == "usted":
        if end == "ar":
            ending = end.replace(end, "a")
            newWord = pro + " " + stem + ending
        elif end == "er" or end == "ir":
            ending = end.replace(end, "e")
            newWord = pro + " " + stem + ending
    elif pro == "ellos" or pro == "ellas" or pro == "ustedes":
        if end == "ar":
            ending = end.replace(end, "an")
            newWord = pro + " " + stem + ending
        elif end == "er" or end == "ir":
            ending = end.replace(end, "en")
            newWord = pro + " " + stem + ending
    else:
        return pronoun + " " + word
    return newWord
def checker( ):
    phraseList = ['yo hablo', 'yo aprendo', 'yo escribo', 'tu hablas', 'tu aprendes', 'tu escribes', 'nosotros hablamos', 'nosotros aprendemos', 'nosotros escribimos', 'el habla', 'el aprende', 'el escribe', 'ella habla', 'ella aprende', 'ella escribe', 'usted habla', 'usted aprende', 'usted escribe', 'ellos hablan', 'ellos aprenden', 'ellos escriben', 'ellas hablan', 'ellas aprenden', 'ellas escriben', 'ustedes hablan', 'ustedes aprenden', 'ustedes escriben', 'blah hablar', 'blah aprender', 'blah escribir']
    p, wrongList = [], []
    for pro in "yO Tu nOsOtros eL elLa uSted eLlOs ellas usTedEs blAh".split():
        for ve in "haBlAr APRenDer ESCriBiR".split():
            p.append(conjug(pro,ve))

