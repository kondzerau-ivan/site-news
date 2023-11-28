Test Extension — Site News

    Data structure

        Total two tables

News table with fields:

• id (primary key)
• title (text)
• status (indexed integer field)
• date (datetime, indexed).

Table linking news items to store:

• id (primary key)
• news_item_id (linking this table with first one)
• store_id (int)

Please note that news item can be switched on for store_id=1 and disabled for
store_id=3

    Admin interface

        Menu structure

Site News
 - Add item
 - News list
 - Settings (leads to module settings)

        Add/Edit Interface

Two possible ways to implement:
 - Standard Magento form widget with fields
 - UI form based on form component (new approach)

        Fields:

 • Title(required)
 • Date (default now, required)
 • Store selector (multiselect) with all store views option (required, default all store
views)
 • Status (default «Enabled»)
Form container must contain buttons:
 • Back
 • Delete
 • Save (redirecting to «Records list» after save)
 • Save & Continue Edit

        Records List

Two possible ways to implement:
 - Page containing standard Magento grid widget with columns
 - UI listing based on listing (grid) component (new approach)

        Columns:

 • ID
 • Title
 • Date
 • Status («Enabled» or «Disabled»)
 • Action (Edit, Delete)
Grid must be filterable by:
 • ID
 • Title
 • Status
 • Date
and sortable by:
 • ID
 • Title
 • Date

        Module Settings

Settings tab is placed at:

 Stores > Configuration > News > Site News

There are two fields there

 • Enabled (Yes/No select), default yes
 • Title (text field), default «Site News»

        Frontend

Extension provides separate page at Customer Area (accessible after customer login at My Account section) containing only records with status «Enabled» and matching current store view (please create 3 stores for testing purpose before in backend).

News are sorted by date descending (later first)

All extension output is placed under menu item which is called according to backend
settings.
