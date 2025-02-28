=========
Australia
=========

.. _australia/employment-hero:

KeyPay Australian Payroll
=========================

The KeyPay Module synchronizes payslip accounting entries (e.g., expenses, social charges,
liabilities, taxes) from Employment Hero to Odoo automatically. Payroll administration is still done
in Employment Hero. We only record the journal entries in Odoo.

.. important::
   KeyPay was rebranded as **Employment Hero** in March 2023.

Configuration
-------------

#. :ref:`Activate <general/install>` the :guilabel:`Keypay Australian Payroll` module (technical
   name: `l10n_au_keypay`).
#. Configure the **KeyPay API** by going to :menuselection:`Accounting --> Configuration -->
   Settings`. More fields become visible after clicking on :guilabel:`Enable KeyPay Integration`.

   .. image:: australia/keypay-integration.png
      :alt: Enabling KeyPay Integration in Odoo Accounting displays new fields in the settings

   - You can find the API Key in the :guilabel:`My Account` section of the Employment Hero platform.

     .. image:: australia/employment-hero-myaccount.png
        :alt: "Account Details" section on the Employment Hero dashboard

   - The **Payroll URL** is pre-filled with `https://keypay.yourpayroll.com.au`. *Please do not
     change it.*
   - You can find the **Business ID** in the KeyPay URL. (i.e., `189241`)

     .. image:: australia/employment-hero-business-id.png
        :alt: The Employment Hero "Business ID" number is in the URL

   - You can choose any Odoo journal to post the payslip entries.

How does the API work?
----------------------

The API syncs the journal entries from Employment Hero to Odoo and leaves them in draft mode. The
reference includes the Employment Hero payslip entry ID in brackets for the user to easily retrieve
the same record in Employment Hero and Odoo.

.. image:: australia/employment-hero-journal-entry.png
   :alt: Example of a Employment Hero Journal Entry in Odoo Accounting (Australia)

By default, the synchronization happens once per week. You can fetch the records manually by going
to :menuselection:`Accounting --> Configuration --> Settings` and, in the :guilabel:`Enable KeyPay
Integration` option, click on :guilabel:`Fetch Payruns Manually`.

Employment Hero payslip entries also work based on double-entry bookkeeping.

The accounts used by Employment Hero are defined in the section :guilabel:`Payroll settings`.

.. image:: australia/employment-hero-chart-of-accounts.png
   :alt: Chart of Accounts menu in Employment Hero

For the API to work, you need to create the same accounts as the default accounts of your Employment
Hero business (**same name and same code**) in Odoo. You also need to choose the correct account
types in Odoo to generate accurate financial reports.
