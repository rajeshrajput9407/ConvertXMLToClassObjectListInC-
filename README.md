# ConvertXMLToClassObjectListInC-
Convert XML To Class Object List In C#
```

IntelliLockDB.ILDataBase db = DBHelper.GetDataBase();
        var allRecords = db.Customers.ToXml();

        NewDataSet1 newDataSetList = new NewDataSet1();
        XmlSerializer serializer = new XmlSerializer(typeof(NewDataSet1));
        StringReader rdr = new StringReader(allRecords);
        NewDataSet1 resulting = (NewDataSet1)serializer.Deserialize(rdr);
        foreach (var item in resulting.Customers)
        {
            Customer licenseTrack = new Customer();
            newDataSetList.Customers.Add(new Customer
            {
                EMail = item.EMail,
                CustomerID =item.CustomerID
            });


            return allRecords;
        }
        return null;
        
        
        /////////////////////CLass .////////////////////
        using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Xml.Serialization;

/// <summary>
/// Summary description for Customer
/// </summary>

// NOTE: Generated code may require at least .NET Framework 4.5 or .NET Core/Standard 2.0.

[XmlRoot(ElementName = "NewDataSet")]
public class NewDataSet1
{
    [XmlElement(ElementName = "Customer")]
    public List<Customer> Customers { get; set; }
}

[XmlRoot(ElementName = "Customer")]
public class Customer
{
    [XmlElement(ElementName = "Company")]
    public string Company { get; set; }

    [XmlElement(ElementName = "EMail")]
    public string EMail { get; set; }

    [XmlElement(ElementName = "CustomerID")]
    public string CustomerID { get; set; }
}

        ```
