design="This code is created by [SHUBH  DIXIT]"
deposite=0
fd=0
rd=0
interst=5
#resistration (ON)
name="shubh dixit"#input("enter your name here:")
if (len(name)==0)or(name.isdigit()):  
    print("enter the name firs")
    name=0
fname="rahul dixit"#input("entrer your father name here:") 
if (len(fname)==0)or(fname.isdigit()):     
    print("enter your father name first")     
    fname=0
mname="jyoti dixit"#input("enter the your mother name here:") 
if (len(mname)==0)or(mname.isdigit()):     
    print("enter your mother name first")     
    mname=0
age=18#int(input("enter the your age here:")) 
print(" the date,mounth and year in date of birth is entered seperatly ") 
date=29#int(input("enter the date when you were born:")) 
mounth="aug"#input("enter the mounth when your were born:") 
year=2005#int(input("enter the year when you were born:")) 
if (2023-age!=year):     
    print("i gess you have entered wrong year or age")     
    age=0     
    date=0     
    mounth=0     
    year=0 
ph="1234567899"#input("enter your phone number here:") 
if (len(ph)!=10):     
    print("i gess your phone number is incorrect")     
    ph=0
print("your pass word must be in integer only")
pas=""
pas1=8826#int(input("enter your password here:"))
pas2=8826#int(input("confirm your password:"))
pas1,pas2=str(pas1),str(pas2)
if (len(pas1)<4):
    zpas=(4-len(pas1))*"0"
    pas1=zpas+pas1
if (len(pas2)<4):
    zpas=(4-len(pas2))*"0"
    pas2=zpas+pas2
if (pas1!=pas2):
    print("please recheck your password")
elif (len(pas1)>4)and(len(pas2)>4):
    print("you can enter 4 digit password only")
elif (pas1==pas2):
    pas=pas1
    pas=int(pas)
job="student"#input("what is your profession:") 
if (len(job)==0):     
    print("fill the job first") 
    job=0 
income=50000#int(input("enter your mounthly income:")) 
#resistration (OFF)  
if (name!=0)and(fname!=0)and(mname!=0)and(age!=0)and(date!=0)and(mounth!=0)and(year!=0)and(ph!=0)and(job!=0)and(design=="This code is created by [SHUBH  DIXIT]")and(pas!=0):     
    print("congratulations your resistration has completed and your bank account has been created thank you for being a part of our family")
    print("this system contain some certain amount of tasks like deposite,wedraw,transaction")
    nft=int(input("how maney task you want to perform:"))
    for i in range(1,nft+1):
        task=input("enter the task here:")
        task=task.casefold()
#Deposite (ON)        
        if (task=="deposite"):
            dep=input("In wich deposite you want to add money:")
            depch=dep.casefold()
            if (depch=="account balence")or(depch=="ab"):
                deposite=int(input("enter the amount you want to deposite in your account:"))
                print("you have successfully added",deposite,"Rs to your account")
                if (depch=="fix deposite") or(depch=="fd"):
                            if (fd>0):
                                fd=int(input("etner the amount you want to deposite in your FD:"))
                                print("you have successfully added",fd,"Rs in your FD")
                            elif(fd<=0):
                                print("creat your FD first")
                if (depch=="recurring deposite")or(depch=="rd"):
                    if (rd>0):
                        rd=int(input("enter the amount you want to deposite in your RD:"))
                        print("you have succesfully added",rd,"Rs in your RD")
                    elif(rd<=0):
                        print("creat your rd first")
                if (depch.isdigit()):
                    print("enter your choise carefully")
#Deposite (OFF)
#Wedraw (ON)
        if (task=="wedraw"):
            w=input("enter the type in wich you want to wedraw:")
            wed=w.casefold()
            if (wed=="account balence")or(wed=="ab"):
                wedraw=int(input("enter the how much amount you want to wedraw:"))
                wpas=int(input("etner the your password:"))
                if (deposite>=wedraw)and (wpas==pas):
                    deposite=deposite-wedraw
                    print("you have taken",wedraw,"Rs from your accout")
                elif(wpas!=pas):
                    print("password is incorrect")
                elif(deposite<wedraw):
                    print("you dont have enough money in your account")
            if(wed=="fix Deposite")or(wed=="fd"):
                print("your have to break your FD to wedraw money from your FD after break the amount will be transfored to your bank account")
                f=input("do you really want to break your FD yes/no:")
                f=f.casefold()
                wfdpas=int(input("etner te your FD password:"))
                if (f=="yes")and (wfdpas==fdpas):
                    deposite=deposite+fd
                    print("you have broken your FD successfully")
                elif(wfdpas!=fdpas):
                    print("incorrect password")
                elif(f=="no"):
                    print("OK, you can also break it later")
                elif(len(f)==0):
                    print("enter your choise please")
                else:
                    print("enter carefully")
            if (wed=="reccuring deposite")or(wed=="rd"):
                r=input("do you really want to break your RD yes/no:")
                print("you have to break your RD to wedraw money  from it after breaking your RD the amount will be transfered to your bank account")
                r=r.casefold()
                wrdpas=int(input("enter your RD password:"))
                if (r=="yes")and(wrdpas==rdpas):
                    deposite=deposite+rd
                    print("you have borken your Rd successfully")
                    rd=0
                elif(wrdpas!=rdpas):
                    print("incorrect password")
                elif(r=="no"):
                    print("you can break it later")
                elif(len(r)==0):
                    print("enter the your decsion please")
                else:
                    print("enter carefully")
#wedraw (OFF)                    
#Transaction (ON)
        if (task=="transaction"):
            tname=input("enter the name of the person you want to transact with:")
            if (name==tname):
                print("you can not enter your name")
            elif(len(tname)==0):
                print("enter name first")
                tname=0
            tph=input("enter the phone number of the person:")
            if (ph==tph):
                print("you can not enter your phone no.")
                tph=0
            elif(len(tph)==0):
                print("enter phone number first")
                tph=0
            if (tname!=0)and(tph!=0):
                tam=int(input("enter the amount of money you want to transfer:"))
                tpas=int(input("enter your password:"))
                if (tam<deposite)and (tpas==pas):
                    print("you have transfered",tam,"Rs to",tname,"account")
                    deposite=deposite-tam
                elif(tpas!=pas):
                    print("incorrect password")
                elif(tam>deposite):
                    print("you dont have enogh money")
            else:
                print("enter the imformation carefully")
#Transaction (OFF)
#FD (ON)
        if (task=="fix deposite")or(task=="fd"):
            print("to creat your FD you have to fill some documents first")
            fdn=input("enter the your name here:")
            if (fdn!=name)or(fdn.isdigit()):
                print("enter your correct name")
                fdn=0
            elif(len(fdn)==0):
                print("enter name first")
                fdn=0
            fdph=input("enter your phone number here:")
            if (fdph!=ph):
                print("enter the your correct number")
                fdph=0
            elif(len(fdph)==0):
                print("enter the phone number first")
                fdph=0
            fdno=input("entrer the name of your nominee here:")
            if(len(fdno)==0):
                print("enter the nominee name first")
                fdno=0
                fdpas=""
            fdpas1=int(input("enter your password here:"))
            fdpas2=int(input("confirm your password:"))
            fdpas1,fdpas2=str(fdpas1),str(fdpas2)
            if (len(fdpas1)<4):
                fdzpas=(4-len(fdpas1))*"0"
                fdpas1=fdzpas+fdpas1
            if (len(fdpas2)<4):
                fdzpas=(4-len(fdpas2))*"0"
                fdpas2=fdzpas+fdpas2
            if (fdpas1!=fdpas2):
                print("please recheck your password")
            elif (len(fdpas1)>4)and (len(fdpas2)>4):
                print("you can enter 4 digit password only")
            elif (fdpas1==fdpas2):
                fdpas=fdpas1
                fdpas=int(fdpas)
            fdt=0
            fdt=int(input("enter the time period of your FD(in years):"))
            if (fdt>5):
                print("you can not enter the time more then 5 years")
                fdt=0
            elif(fdt==0):
                print("enter time period first")
                fdt=0
            if (fdn!=0)and(fdph!=0)and(fdno!=0)and(fdt!=0)and(fdpas!=0):
                fdd=int(input("enter the first deposite of your FD:"))
                if (fdd!=0):
                    print("congratulations you have created your FD you will get your money on 5% interst")
                    fd1=(fdd*fdt*interst)/100
                    fd=fd1+fdd
            else:
                print("fill the form carefully")
#FD system (OFF)                
#RD system (ON)                
        if (task=="reccuring Deposite") or (task=="rd"):
            print("too creat RD you have to fill tga form first")
            rd=0
            rdn=input("enter your name:")
            if (rdn!=name):
                print("enter the your correct name")
                rdn=0
            rdph=input("enter the phone number here:")
            if(ph!=rdph):
                print("enter the correct phone number ")
                rdph=0
            rdno=input("enter the name of your nominee:")
            rdpas=""
            rdpas1=int(input("enter your password here:"))
            rdpas2=int(input("confirm your password:"))
            rdpas1,rdpas2=str(rdpas1),str(rdpas2)
            if (len(rdpas1)<4):
                rdzpas=(4-len(rdpas1))*"0"
                rdpas1=rdzpas+rdpas1
            if (len(rdpas2)<4):
                rdzpas=(4-len(rdpas2))*"0"
                rdpas2=rdzpas+rdpas2
            if (rdpas1!=rdpas2):
                print("please recheck your password")
            elif (len(rdpas1)>4)and (len(rdpas2)>4):
                print("you can enter 4 digit password only")
            elif (rdpas1==rdpas2):
                rdpas=rdpas1
                rdpas=int(rdpas)
            rdt=int(input("enter the time period of your RD(in years):"))
            rdd=int(input("do you want to deposite some money in your RD:"))
            if (rdd==0):
                print("you have to deposite some moey in your RD")
            if (rdn!=0) and (rdph!=0) and (rdno!=0)and(rdd!=0)and(rdt!=0)and(rdpas!=0):
                print("congratulations you have created your RD you will get the money on 5% interst")
                rd1=(rdd*rdt*interst)/100
                rd=rd1+rdd
            else:
                print("please fill the form properly")
#RD system (OFF)
#Check deposite system(ON)  
        if(task=="check deposite")or(task=="cd"):
            cdc=input("enter the wich deposite your want to check:")
            cdc=cdc.casefold()
            if (cdc=="account balence")or(cdc=="ab"):
                cdpas=int(input("enter your password here:"))
                if (cdpas==pas):
                    if (deposite>0):
                        print("you have",deposite,"Rs in your bank account")
                    elif(deposite<=0):
                        print("you dont have any moey in your bank account")
            elif(cdc=="fix deposite")or(cdc=="fd"):
                if(fdpas>0):
                    cdpas=int(input("enter your FD pasword:"))
                    if(cdpas==fdpas):
                        if(fd>0):
                            print("you have",fd,"Rs in your FD")
                        elif(fd<=0):
                            print("you have no money in your FD")
                elif(fdpas==0):
                    print("creat FD first")
            elif(cdc=="reccuring deposite")or(cdc=="rd"):
                if(rdpas>0):
                    cdpas=int(input("enter your RD password:"))
                    if(cdpas==rdpas):
                            if (rd>0):
                                print("you have",rd,"Rs in your RD")
                            elif(rd<=0):
                                print("you dont have any money in your RD")
                elif(rdpas==0):
                    print("creat RD first")
            else:
                print("enter the deposite carefully")
#Check deposite system (OFF)
#Loan system (ON)
        if(task=="loan")or(task=="l"):
            loand=int(input("enter the date:"))
            loanm=int(input("enter the month:"))
            loany=int(input("enter the year here:"))
            loanr=input("enter wich type of loan do you want:")
            loanr=loanr.casefold()
            loan=int(input("etner the amount of loan you want to take:"))
            loanc=input("enter the collateral here:")
            loant=0
            if (loanr=="home loan"):
                if(loan>=1000000)and (loan<2000000):
                    if (income>=10000)and (income<50000):
                        loant=0
                    elif (income>=50000)and (income<100000):
                        loant=0
                    elif (income>=100000) and(income<500000):
                        loant=0
                    elif (income>=500000):
                        loant=0
                elif (loan>=2000000)and (loan<3000000):
                        if (income>=10000)and (income<50000):
                            loant=0
                        elif (income>=50000) and(income<100000):
                            loant=0
                        elif (income>=100000) and(income<500000):
                            loant=0
                        elif (income>=500000):
                            loant=0
                elif(loan>=3000000) and(loan<4000000):
                        if(income>=10000) and(income<50000):
                            loant=0
                        elif(income>=50000) and(income<100000):
                            loant=0
                        elif(income>=100000) and(income<500000):
                            loant=0
                        elif(income>=500000):
                            loant=0
                elif(loan>=4000000) and(loan<=5000000):
                        if (income>=10000) and(income<50000):
                            loant=0
                        elif(income>=50000) and(income<100000):
                            loant=0
                        elif(income>=100000) and(income<500000):
                            loant=0
                        elif(income>=500000):
                            loant=0
                        l=(loan)/loant
                        l=l/30
                        import math
                        l=math.ceil(l)
                        print("you have taken a loan of",loan,"you have to give",l,"Rs per mounth till",loant,"year")                             
else:
    print("fill the resistration details properly ")
print(design)










