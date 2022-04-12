# Primeiro teste

## Segundo teste

Terceiro teste

``` python 
def openFile():
    global df
    filepath = filedialog.askopenfilename(
        initialdir="/Desktop", title="", filetypes=(("csv files", "*.csv"), ("all files", "*.*")))
    file = open(filepath, 'r')
    my_label = Label(app, text=filepath).pack()
    df = pd.read_csv(filepath, encoding='UTF-8', sep=',', names=['Com', 'Banco', 'Agencia', 'Conta Dest.', 'Cod Dev', 'Lote', 'Pos.', 'n0', 'n1', 'Ban', 'Agen',
                                                                 'Ag Dep', 'Conta', 'Nº CH', 'TD', 'Valor', 'Ocorrencia', 'Data', 'n2', 'n3', 'n4', 'n5', 'Valor1', 'Valor2', 'PAC Cliente', 'PA Dep', 'PAC Cliente1', 'n6', 'Canal'])

    df = df.drop(columns=['Com', 'Conta Dest.', 'Lote', 'Pos.', 'n0', 'n1', 'Ban', 'Agen',
                 'TD', 'n2', 'n3', 'n4', 'n5', 'Valor1', 'Valor2', 'PAC Cliente1', 'n6', 'Canal'])

    # PASSAR A COLUNA DE OCORRENCIAS PARA O FINAL
    df = df[['Banco', 'Agencia', 'Cod Dev', 'Ag Dep', 'Conta', 'Nº CH',
             'Valor', 'Data', 'PAC Cliente', 'PA Dep', 'Ocorrencia']]

    # CONVERTER A DATA
    df['Data'] = pd.to_datetime(df['Data'])
    df['Data'] = df['Data'].dt.strftime('%d/%m/%Y')


```

