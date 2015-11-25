Public Class Form1


    Private myPrice() As Double
    Private myProduct() As String

    Dim _myMeter As String
    Dim _test As String
    Dim strOutput As String

    Dim antal As Double
    Dim produkt As String

    Dim myKvitto As Kvitto

    Function ValidateAntal() As Boolean
        Dim okey As Boolean = False

        If IsNumeric(txtQuan.Text) Then
            antal = CInt(txtQuan.Text)
            If antal > 0 And antal < 100 Then
                _myMeter = antal
                okey = True
            End If
        End If

        Return okey


    End Function

    Public Sub New()

        ' This call is required by the designer.
        InitializeComponent()

        ' Add any initialization after the InitializeComponent() call.

        TextBoxInAddMode()
        LoadArrays()
        SetupComboBox()

        Bibblan()


        main()


    End Sub
    Sub main()
        myKvitto = New Kvitto With {.AntalPengar = 0} 'Properties, Längd _
        'och Produkt också


    End Sub


    Public Sub kvitto()

        strOutput = strOutput & "BrädProdukt: " & cmbItems.SelectedItem & Environment.NewLine &
            "Antal Meter: " &
            txtQuan.Text & Environment.NewLine & Environment.NewLine & "Ditt Pris: " & myKvitto.AntalPengar & Environment.NewLine _
            & Environment.NewLine

        txtRec.Text = strOutput
    End Sub

    Private Sub LoadArrays()

        myProduct = {"2x2", "2x3", "2x4"}

        myPrice = {12.9, 18.2, 23.1}

    End Sub

    Private Sub SetupComboBox()
        ' Rensa combobox
        cmbItems.Items.Clear()

        '' Loopa igenom myProdukt och lägg till Item i Combobox
        'For Each product In myProduct
        '    cmbProdukt.Items.Add(product)
        'Next

        cmbItems.Items.AddRange(myProduct)

    End Sub

#Region "Biblioteket"
    'behöver count += 1 funktion

    'stringen ska fås genom kvittot


    Sub Bibblan()
        Dim i As Integer
        ' Put two Integer keys into Dictionary Of Integer.
        Dim dictionary As New Dictionary(Of Integer, String)

        'dictionary ska ökas här varje gång du klickar på Lägg Till
        dictionary.Add(1, "Bill")
        dictionary.Add(2, "Steve")

        '____________________________________________________________________________
        '==============================test Zone ====================================
        If btnAdd.PerformClick Then
            i += 1

            dictionary.Add((i), "Mike")
        End If
        '==============================test Zone ====================================


        'See If this key exists.
        If dictionary.ContainsKey(FindKey(txtUndo.text)) Then
            ' Print value at this key.
            txtQuan.Text = "Bibblan funkar"
        End If
    End Sub

    Sub ArtikelText(ByRef valueIn As String)

    End Sub
    Function FindKey(ByVal IndexIn As Integer) As Integer
        IndexIn = txtUndo.text
    End Function

#End Region




#Region "Knappar"
    Private Sub cmbItems_SelectedIndexChanged(sender As Object, e As EventArgs) Handles cmbItems.SelectedIndexChanged
        'txtRec.Text = myPrice(cmbItems.SelectedIndex).ToString
        'kvitto()
        LoadArrays()


        'If cmbItems = cmbItems.Items(0) Then
        '    txtQuan.Text = CInt(txtQuan.Text)

        '    myKvitto.AntalPengar += (20 * txtQuan.Text)



        'ElseIf cmbItems.Items(1) Then  '(1) är andra alternativeti dropboxen?
        '    myKvitto.AntalPengar += (30 * txtQuan.Text)
        'End If


        'If cmbItems = cmbItems.Items(12.9) Then
        '    mykvitto.AntalPengar += 15
        'End If


    End Sub



    Private Sub btnPay_Click(sender As Object, e As EventArgs) Handles btnPay.Click
        If Not IsNothing(txtRec) Then
            'TODO skriv så att LoginForm1 kommer upp!

            LoginForm1.Show()
            LoginForm1.setMoney(myKvitto.AntalPengar)

        End If
    End Sub

    Private Sub btnClear_Click(sender As Object, e As EventArgs) Handles btnClear.Click

        Clear()
        strOutput = String.Empty
        txtRec.Text = strOutput
        myKvitto.AntalPengar = 0
        TextBoxInAddMode()

    End Sub
    Public Function Clear()

        txtQuan.Text = String.Empty

    End Function


    Private Sub btnCopy_Click(sender As Object, e As EventArgs)
        MessageBox.Show("Fredric LA was here")


    End Sub

    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

        If ValidateAntal() = True Then
            beräkna()
            kvitto()
            TextBoxInPayAndClearMode()
        End If



    End Sub

    Sub beräkna()

        produkt = cmbItems.SelectedIndex
        antal = txtQuan.Text



        If cmbItems.SelectedIndex = 0 Then
                myKvitto.AntalPengar += myPrice(0) * antal


            ElseIf cmbItems.SelectedIndex = 1 Then
                myKvitto.AntalPengar += myPrice(1) * antal
            ElseIf cmbItems.SelectedIndex = 2 Then
                myKvitto.AntalPengar += myPrice(2) * antal
            ElseIf cmbItems.SelectedIndex = 3 Then
                myKvitto.AntalPengar += myPrice(3) * antal
            End If


    End Sub


#End Region

#Region "txtboxes modes"



    Private Sub TextBoxInAddMode()

        btnAdd.Enabled = True
        btnClear.Enabled = False
        txtQuan.Enabled = True
        cmbItems.Enabled = True
        btnPay.Enabled = False

    End Sub

    Private Sub TextBoxInPayAndClearMode()

        btnAdd.Enabled = True
        btnClear.Enabled = True
        txtQuan.Enabled = True
        cmbItems.Enabled = True
        btnPay.Enabled = True

    End Sub

    Private Sub txtQuan_TextChanged(sender As Object, e As EventArgs) Handles txtQuan.GotFocus
        txtQuan.SelectAll()


    End Sub




#End Region

End Class
