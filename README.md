# Formativas

Actividad formativa 3:

picachu = 4500
otaku = 5000
pulpo = 5200
anguila = 4800

#Menu para realizar tipo y cantidad de pedido

print("¡¡¡Bienvenido a Shushimoto, recuerda que todos los martes tenemos 2x1 en sushi de ballena!!!")
print("Por favor, ingresa el número del pedido que deseas realizar")
opc0 = 0
opc1 = 0
exc = 0
pica_num = 0
otaku_num = 0
pulpo_num = 0
anguila_num = 0
while opc0 == 0:
    while opc1 == 0:
        print("1 = Picachu Roll")
        print("2 = Otaku Roll")
        print("3 = Pulpo Venenoso Roll")
        print("4 = Anguila Eléctrica Roll")
        print("5 = Continuar al metodo de pago")
        print("6 = Cancelar y salir")
        print(" ")
        x = int(input("Opción a elegir: "))
        
        if x > 0 and x < 5:
            if x == 1:
                pica_cont = int(input("Cantidad a pedir: "))
                resp = str(input("¿Quiere realizar otro pedido?: "))
                pica_num = pica_num + pica_cont
                if resp == "no":
                    opc1 = 1
            elif x == 2:
                otaku_cont = int(input("Cantidad a pedir: "))
                resp = str(input("¿Quiere realizar otro pedido?: "))
                otaku_num = otaku_num + otaku_cont
                if resp == "no":
                    opc1 = 1
            elif x == 3:
                pulpo_cont = int(input("Cantidad a pedir: "))
                resp = str(input("¿Quiere realizar otro pedido?: "))
                pulpo_num = pulpo_num + pulpo_cont
                if resp == "no":
                    opc1 = 1
            elif x == 4:
                anguila_cont = int(input("Cantidad a pedir: "))
                resp = str(input("¿Quiere realizar otro pedido?: "))
                anguila_num = anguila_num + anguila_cont
                if resp == "no":
                    opc1 = 1
        elif x == 5:
            opc1 = 1
        elif x == 6:
            opc1 = 1
            exc = 1

    #Canjear código para la obtención de descuento

    opc2 = 0
    descuento = 1
    if exc == 0:
        while opc2 == 0:
            print(" ")
            resp = str(input("¿Tienes algún código de descuento?: "))
            if resp == "si":
                
                resp2 = str(input("Ingrese el código: "))
                if resp2 == "soyotaku":
                    print("Código canjeado con exito")
                    descuento = 0.9
                    opc2 = 1
                else:
                    print("Código no valido")
            else: opc2 = 1

    #Costos y calculo de total

    valor_pica = pica_num * picachu
    valor_otaku = otaku_num * otaku
    valor_pulpo = pulpo_num * pulpo
    valor_anguila = anguila_num * anguila
    valor_sub = (valor_otaku + valor_anguila + valor_pica + valor_pulpo)
    if descuento == 0.9:
        valor_desc = valor_sub * 0.1
    else: valor_desc = 0
    valor_final = valor_sub * descuento
    cantidad_total = pica_num + otaku_num + pulpo_num + anguila_num

    #Pantalla final

    print(" ")
    print("* * * * * * * * * *")
    print("TOTAL PRODUCTOS:",cantidad_total)
    print("* * * * * * * * * *")
    print("Pikachu Roll:",pica_num)
    print("Otaku Roll:",otaku_num)
    print("Pulpo Roll:",pulpo_num)
    print("Anguila Eléctrica Roll:",anguila_num)
    print("* * * * * * * * * * * * * *")
    print("Subtotal a pagar:",valor_sub)
    print("Descuento por código:",valor_desc)
    print("TOTAL:",valor_final)
    print(" ")
    resp3 = str(input("¿Quieres realizar otro pedido?: "))
    if resp3 == "no":
        print("!!Gracias por confiar en nosotros, que disfrutes tu pedido¡¡")
        opc0 = 1
    elif resp3 == "si":
        opc1 = 0
        pica_num = 0
        otaku_num = 0
        pulpo_num = 0
        anguila_num = 0
