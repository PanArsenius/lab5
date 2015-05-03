# lab5
lab5
double a, b, x, eps, h, d1, d2, pogr,x0,Num;
int n,q;
        a = StrToFloat(Edit1->Text);        b = StrToFloat(Edit2->Text);
        n = StrToInt(Edit3->Text);           q = StrToFloat(Edit4->Text);
        h = (b - a)/n;		
        eps=0,001 ;
                Chart2->Series[0]->Clear();
        for(x = a-h; x< b+h; x+=h)
                Chart2->Series[0]->AddXY(d1,fun(x));
                x0=x+eps;
                d1=(fun(x) - fun(x0))/(x - x0);
        Num = (fun(x + eps) - fun(x0 + eps))/((x + eps) - (x0 + eps)) - (fun(x) - fun(x0))/(x - x0);
         d2 = Num/eps;
         Chart2->Series[0]->AddXY(d1,fun(x));
         Memo2->Lines->Add("d1 = " + FloatToStrF(d1,ffFixed,8,q)+"     d2 ="+FloatToStrF(d2,ffFixed,8,q));
}
