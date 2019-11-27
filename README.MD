
Sitecore Commerce Engine VERTEX Tax plugin (Sitecore Experience Commerce 9.1)
======================================

This plugin allows the user to integrate VERTEX as a tax calculation Method for the ecommerce site. 
- It is very easy to integrate or extend to fit your needs.
- It will fetch tax rates from VERTEX based on the item type and price and of the items in your cart or cartline.


Grouping
========
This is a Tax plugin using VERTEX Api

Sponsor
=======
This plugin was sponsored and created by XCentium.

How to Install
==============

1. Copy it to your Sitecore Commerce Engine Solution and add it as a project 

2. Add it as a dependency to your Sitecore Commerce Engine Project

3. Add it as a dependency to your Adventure works or Habitat or Custom Site plugin' project

4. Create a json file named "Plugin.Xcentium.Tax.Vertex.PolicySet-1.0.0.json" under your "Sitecore.Commerce.Engine"'s Environment folder. Add the json content below, set your Vertex API credentials in the json below

```
{
  "$type": "Sitecore.Commerce.Core.PolicySet, Sitecore.Commerce.Core",
  "Id": "Entity-PolicySet-VertexPolicySet",
  "Version": 1,
  "IsPersisted": false,
  "Name": "VertexPolicySet",
  "Policies": {
    "$type": "System.Collections.Generic.List`1[[Sitecore.Commerce.Core.Policy, Sitecore.Commerce.Core]], mscorlib",
    "$values": [
    {
        "$type": "Plugin.Xcentium.Vertex.Tax.VertexPolicy, Plugin.Xcentium.Vertex.Tax",
        "ClassCode": "XXXXXXXXXXX",
        "CustomerCode": "XXXXXXXXXXX",
        "UserName": "XXXXXXXXXXX",
        "Password": "XXXXXXXXXXX",
        "InProductionMode": "false",
        "ShipFromAddressLine1": "615 N Nash Street",
        "ShipFromAddressLine2": "303",
        "ShipFromAddressLine3": "",
        "ShipFromCity": "El Segundo",
        "ShipFromStateOrProvinceCode": "CA",
        "ShipFromPostalCode": "90245",
        "ShipFromCountryCode": "US",
        "PolicyId": "AvalaraPolicy",
        "Models": {
        "$type": "System.Collections.Generic.List`1[[Sitecore.Commerce.Core.Model, Sitecore.Commerce.Core]], mscorlib",
        "$values": [
        ]
        }
    }
    ]
  }
}



```

Inside your corresponding json files for PlugIn.Habitat.CommerceAuthoring-1.0.0.json, PlugIn.Habitat.CommerceMinions-1.0.0.json and PlugIn.Habitat.CommerceShops-1.0.0.json
 you will need to add the line below. I added mine after braintree entry

 ```
       {
        "$type": "Sitecore.Commerce.Core.PolicySetPolicy, Sitecore.Commerce.Core",
        "PolicySetId": "Entity-PolicySet-VertexPolicySet"
      },


```

5. Replace XXXXXXXXXXX above with the API connection details you got when you registered with Vertex,  add your ship from address.


6. You are ready to start using it. 

Note:
=====
- Remember to register with Vertex and get your API connection details. Also activate your registration and set your Vertex choices.

- If you have any questions, comment or need us to help install, extend or adapt to your needs, do not hesitate to reachout to us at XCentium ask about Sitecore Commerce Engine Vertex Plugin.






