design="This code is created by [SHUBH  DIXIT]"
loan1=0
loan=0
th={}
rdpas=0
fdpas=0
deposit=0
fd=0
rd=0
interst=5
#resistration (ON)
name="shubh dixit"#input("enter your name here:")
if (len(name)==0)or(name.isdigit()):  
    print("enter the name first")
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
if (ph.isdigit()==True):
    if (len(ph)!=10):
        print("i gess your phone number is incorrect")
        ph=0
elif (ph.isdigit()==False):
    print("enter the phone number in integer")
    ph=0
pas=""
pas1="8826"#input("enter your password here:")
pas2="8826"#input("confirm your password:")
if (pas1.isdigit()==True)or(pas2.isdigit()==True):
    if (len(pas1)<4):
        zpas=(4-len(pas1))*"0"
        pas1=zpas+pas1
    if (len(pas2)<4):
        zpas=(4-len(pas2))*"0"
        pas2=zpas+pas2
    if (pas1!=pas2):
        print("please recheck your password")
        pas=0
    elif (len(pas1)>4)and(len(pas2)>4):
        print("you can enter 4 digit password only")
        pas=0
    elif (pas1==pas2):
        pas=pas1
        pas=int(pas)
    else:
        print("enter the password carefully")
        pas=0
elif(pas1.isdigit()==False)or(pas2.isdigit()==False):
    print("enter the passward in integer only")
    pas=0
job="student"#input("what is your profession:") 
if (len(job)==0):     
    print("fill the job first") 
    job=0 
income=100000#int(input("enter your mounthly income:")) 
#resistration (OFF)  
if (name!=0)and(fname!=0)and(mname!=0)and(age!=0)and(date!=0)and(mounth!=0)and(year!=0)and(ph!=0)and(job!=0)and(design=="This code is created by [SHUBH  DIXIT]")and(pas!=0):     
    print("congratulations your resistration has completed and your bank account has been created thank you for being a part of our family")
    print("this system contain some certain amount of tasks like deposit,wethdraw,transaction")
    while True:
        task=input("enter the task here:")
        task=task.casefold()
#Deposit (ON)        
        if (task=="deposit"):
            dep=input("In wich deposit you want to add money:")
            depch=dep.casefold()
            if (depch=="account")or(depch=="a"):
                if (deposit==0):
                    deposit=int(input("enter the amount you want to deposit in your account:"))
                    print(f"you have successfully added {deposit}Rs to you account")
                elif (deposit>0):
                    deposit2=0
                    deposit2=int(input("enter the amount of money you want to deposit in your account:"))
                    deposit=deposit+deposit2
                    print(f"you have successfully added {deposit}Rs to your account")
            if (depch=="fix deposit") or(depch=="fd"):
                            if (fd>0):
                                fd=int(input("etner the amount you want to deposit in your FD:"))
                                print("you have successfully added",fd,"Rs in your FD")
                            elif(fd<=0):
                                print("creat your FD first")
            if (depch=="recurring deposit")or(depch=="rd"):
                    if (rd>0):
                        rd=int(input("enter the amount you want to deposit in your RD:"))
                        print("you have succesfully added",rd,"Rs in your RD")
                    elif(rd<=0):
                        print("creat your rd first")
            if (depch.isdigit()==True):
                    print("enter your choise carefully")
#Deposit (OFF)
#Wethdraw (ON)
        if (task=="wethdraw"):
                wethdraw=int(input("enter the how much amount you want to wethdraw:"))
                wpas=int(input("etner the your password:"))
                if (deposit>=wethdraw)and (wpas==pas):
                    deposit=deposit-wethdraw
                    print("you have taken",wethdraw,"Rs from your accout")
                elif(wpas!=pas):
                    print("password is incorrect")
                elif(deposit<wethdraw):
                    print("you dont have enough money in your account")
#wethdraw (OFF)                    
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
                if (tam<deposit)and (tpas==pas):
                    print("you have transfered",tam,"Rs to",tname,"account")
                    deposit=deposit-tam
                elif(tpas!=pas):
                    print("incorrect password")
                elif(tam>deposit):
                    print("you dont have enogh money")
            else:
                print("enter the imformation carefully")
            th[tname]=tph,tam
            print(th)
#Transaction (OFF)
#Transaction history (ON)
        if(task=="transaction history")or    (task=="th"):
            print(f"[Name]:[Phone no.]:  [ammount]")
            for x,y in th.items():
                print(x,":",y)
#Transaction history (OFF)
#FD (ON)
        if (task=="fix deposit")or(task=="fd"):
          if (fd==0):
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
                fdd=int(input("enter the first deposit of your FD:"))
                if (fdd!=0):
                    print("congratulations you have created your FD you will get your money on 5% interst")
                    fd1=(fdd*fdt*interst)/100
                    fd=fd1+fdd
            elif(fdn==0)or(fdph==0)or (fdno==0)or(fdt==0)or(fdpas==0):
                print("fill the form carefully")
          elif (fd>0):
              f=input("do you really want to break your FD yes/no:")
              f=f.casefold()
              wfdpas=int(input("etner te your FD password:"))
              if (f=="yes")and (wfdpas==fdpas):
                    deposit=deposit+fd
                    print("you have broken your FD successfully")
              elif(wfdpas!=fdpas):
                    print("incorrect password")
              elif(f=="no"):
                    print("OK, you can also break it later")
              elif(len(f)==0):
                    print("enter your choise please")
              else:
                    print("enter carefully")
#FD system (OFF)                
#RD system (ON)                
        if (task=="reccuring Deposite") or (task=="rd"):
            if(rd==0):
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
                rdd=int(input("do you want to deposit some money in your RD:"))
                if (rdd==0):
                    print("you have to deposit some moey in your RD")
                if (rdn!=0) and (rdph!=0) and (rdno!=0)and(rdd!=0)and(rdt!=0)and(rdpas!=0):
                    print("congratulations you have created your RD you will get the money on 5% interst")
                    rd1=(rdd*rdt*interst)/100
                    rd=rd1+rdd
                else:
                    print("please fill the form properly")
            elif(rd>0):
                 r=input("do you really want to break your RD yes/no:")
                 print("you have to break your RD to wethdraw money  from it after breaking your RD the amount will be transfered to your bank account")
                 r=r.casefold()
                 wrdpas=int(input("enter your RD password:"))
                 if (r=="yes")and (wrdpas==rdpas):
                     deposit=deposit+rd
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
#RD system (OFF)
#Check deposit system(ON)  
        if(task=="check deposit")or(task=="cd"):
            cdc=input("enter the wich deposit your want to check:")
            cdc=cdc.casefold()
            if (cdc=="account")or(cdc=="a"):
                cdpas=int(input("enter your password here:"))
                if (cdpas==pas):
                    if (deposit>0):
                        print("you have",deposit,"Rs in your bank account")
                    elif(deposit<=0):
                        print("you dont have any moey in your bank account")
                elif(cdpas!=fdpas):
                        print("incorrect password")
            elif(cdc=="fix deposit")or(cdc=="fd"):
                if(fdpas>0):
                    cdpas=int(input("enter your FD pasword:"))
                    if(cdpas==fdpas):
                        if(fd>0):
                            print("you have",fd,"Rs in your FD")
                        elif(fd<=0):
                            print("you have no money in your FD")
                elif(fd==0):
                    print("creat FD first")
                elif(fdpas!=cdpas):
                    print("enter the correct pasword")
            elif(cdc=="reccuring deposit")or(cdc=="rd"):
                if(rd>0):
                    cdpas=int(input("enter your RD password:"))
                    if(cdpas==rdpas):
                            if (rd>0):
                                print("you have",rd,"Rs in your RD")
                            elif(rd<=0):
                                print("creat RD first")
                    elif(rdpas!=cdpas):
                        print("enter the correct password please")
                elif(rd==0):
                    print("creat RD first")         
            else:
                print("enter the deposit carefully")
#Check deposit system (OFF)
#Loan system (ON)
        if(task=="loan")or(task=="l"):
            if(loan==0):
                loann=input("enter your name here:")
                if(len(loann)==0):
                    print("enter name first")
                    loann=0
                elif(loann.isdigit()==True):
                    print("please enter your name in alphabets only")
                    loann=0
                elif(loann!=name):
                    print("please enter your correct name")
                    loann=0
                loanph=input("enter your phone number here:")
                if (len(loanph)==0):
                    print("enter phone number first")
                    loanph=0
                elif(loanph.isdigit()==False):
                    print("your phone number must be in integers only")
                    loanph=0
                elif(loanph!=ph):
                    print("please enter your correct phone number")
                loand=int(input("enter the current date:"))
                loanm=int(input("enter the current month:"))
                loany=int(input("enter the current year here:"))
                loanr=input("enter wich type of loan do you want:")
                loanr=loanr.casefold()
                loan=int(input("etner the amount of loan you want to take:"))
                loanc=input("enter the collateral here:")
                loant=0
                if loanr == "home loan" or loanr == "hl":
                    loant = 10
                elif loanr == "car loan" or loanr == "cl":
                     loant = 5
                elif loanr == "educational loan":
                     loant = 1                              
                            l=(loan)/loant
                            l=l/30
                            import math
                            l=math.ceil(l)
                            interst=(loan*loant*interst)/100
                            loan1=loan+interst
                            if (loann!=0)and (loanph!=0):
                                print("you have taken a loan of",loan,"after applying interst you have to pay",loan1," in",l,"Rs per mounth till",loant,"year")
                            else:
                                print("enter your details carefully")
                                                                 
#loan system (OFF)
#Help feature (ON)
        if (task=="help"):
            help1=input("in what system you want help:")
            help1=help1.casefold()
            if(help1=="resistration system")or(help1=="rs"):
                help2=input("enter what kind of help do you want:")
                help2=help2.casefold()
                if(help2=="names"):
                    print("it is posible that you are you are not entering the name properly it is importent to remember the names you have entered because contain an importent role in program make sure to not leave it blank ")
                elif(help2=="age"):
                    print("to resister in this program your age must be aove 18 if your age is 18+ and still you are facing problem so you should check your date of birth")
                elif(help2=="date of birth"):
                    print("you have to enter your date,mounth,and your of birth saparatly and mounth should be in characters if you are having error in entering your date of birth it can be possible that you are making any mistake in entering date of birth")
                elif(help2=="phone number"):
                    print("you have to enter your phone number in exact 10 digite make to not enter any character between your number")
                elif(help2=="passward"):
                    print("you have to enter the password in 4 digite and you can enter your password in digite only you can not use character also if you enter the password in less then 4 digite the program will automatically add 0 at the front ")
                elif(help2=="job"):
                    print("youu have to enter youre profession you can enter any type of profession no matter if your a student or house wife")
                elif(help2=="income"):
                    print("you have to enter your mounthly income carefully it help you in getting loan")
            elif(help1=="task"):
                print("at first you have to enter the number of task you want to perform after that you can enter the tasks your want to perform you have to enter the number of task in integer but dont enter the task in integer you can get error")
            elif(help1=="deposit"):
                print("In deposit system fist of all you have to type that what type of deposit you want to have like(if you want to deposit money in your account then simply type account similarly if you have to deposit money in your fd the you have to type fd after that you have to type the ammount of money your want to deposit and thats all if you are still facing problem in using deposit system you can contect the coder")
            elif(help1=="wethdraw"):
                print("to wethdraw your money you first of you have to enter th ammount of money you want to take then enter your password after entering the passsword you get the money easily if you are still facing problem then it mean there must be some mistake in the program you can contect the coder for that")
            elif(help1=="transaction"):
                print("to perform transaction first you have to enter the deetails of the person to wich you want to transfer money after that you have to enter the your account password make sure you have enough money in your account if your stil facing problems in transaction it mean there is some problem in the program you can contect the coder for that")
            elif(help1=="fix deposit")or (help1=="fd"):
                print("as real life to creat your fd you have to fill the document tations after that your fd will created successfully and you can deposit money in your fd by using deposit system and if you want to break you fd then you simply have to enter fd in the task section agin after that the program ask your final decision you have to type yes and enter your fd password there and you can break your fd successfully if your still facing problem you can cntact to coder")
            elif(help1=="reccuring deposit")or (help1=="rd"):
                print("just like real lif to creat your RD you have to fill the  necesery documentation after dong that you have successfully created your RD to deposit monney in your RD you have to use deposit system and to break your RD you simply have to enter rd agin in task section after that the program ask for your final decision and you have to type yes there after that you have to enter your RD password after all this you can successfully break your RD and the money will get transfered o your bank account")
            elif(help1=="loan"):
                print("To get loan just like real life you have to fill the necesery documentation after entering that the program will automatically give the time period and the mounthly payment for your loan for deositing money for your loan you simply have to enter looan in the task section agin then you can fulfill your loan")
            elif(help1=="check deposait") or(help1=="cd"):
                print("this system is the most helpfull system in the allover progrm it will help you to knw how much ammount of money doyour have in your bank account or FD or RD and also show that how much loan you have paid and how much loan is remaining to use it you simply have to enter what ammount you want to see i mean FD,RD or bank account after enterig the choise you have to enter your password and then you can see the ammount if your still facing problem then you can contect the coder")
            elif(help1=="exit"):
                print("to exit from this program you simply hav to type exit in the tak section and then you can see the program end message and the name of coder")
            elif(help1=="help"):
                print("to use help feature you simply have to type the name of system in wich you are facing probem and then you can see the full paragraph about how can you use that system")
            else:
                print("enter your problem carefully")
        if(task=="exit"):
            print("program end")
            print(design)
            break        
else:
    print("fill the resistration details properly ")
    print(design)










