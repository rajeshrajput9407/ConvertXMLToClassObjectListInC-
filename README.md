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
        return null;```
