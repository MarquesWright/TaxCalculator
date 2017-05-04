using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace TaxCalculator
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void btnCalculate_Click(object sender, EventArgs e)
        {
            // retrieve income from the form
            decimal taxableIncome = Convert.ToDecimal(txtTaxableIncome.Text);
            decimal taxOwed = .0m;

            // calculate the tax owed
            if (taxableIncome > 0 && taxableIncome <= 9225)
                taxOwed = ((taxableIncome - 0) * .1m + 0);
            else if (taxableIncome > 9225 && taxableIncome <= 37450)
                taxOwed = ((taxableIncome - 9225) * .15m + 922.5m);
            else if (taxableIncome > 37450 && taxableIncome <= 90750)
                taxOwed = ((taxableIncome - 37450) * .25m + 5156.25m);
            else if (taxableIncome > 90750 && taxableIncome <= 189300)
                taxOwed = ((taxableIncome - 90750) * .28m) + 18481.25m;
            else if (taxableIncome > 189300 && taxableIncome <= 411500)
                taxOwed = ((taxableIncome - 189300) * .33m) + 46075.25m;
            else if (taxableIncome > 411500 && taxableIncome <= 413200)
                taxOwed = ((taxableIncome - 411500) * .35m) + 119401.25m;
            else
                taxOwed = ((taxableIncome - 413200) * .396m) + 119996.25m;

            txtTaxOwed.Text = taxOwed.ToString("n2");
            txtTaxableIncome.Focus();
        }

        private void btnExit_Click(object sender, EventArgs e)
        {
            this.Close();
        }

       
    }
}
