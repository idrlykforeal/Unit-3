# sql console code

```sql
SELECT count(*) from INHABITANT where gender="Male" and state = "Friendly";

SELECT avg(gold) from INHABITANT;

SELECT count(*) from ITEM where item like "A%";

SELECT  job,count(personid) from INHABITANT group by  job;

SELECT * from ITEM where owner
```

# proof 

<img width="332" alt="image" src="https://user-images.githubusercontent.com/100017195/224199516-e123c998-1639-41be-8324-5fd9c1b398af.png">
<img width="332" alt="image" src="https://user-images.githubusercontent.com/100017195/224199525-61f95d7e-1527-45f8-83dd-b0c93b284d59.png">
<img width="332" alt="image" src="https://user-images.githubusercontent.com/100017195/224199552-ee17f846-fe59-421e-910f-65062f0b21bf.png">
<img width="434" alt="image" src="https://user-images.githubusercontent.com/100017195/224199587-1c45ba8e-0f4f-4f44-850d-89c6a15e8fbf.png">
<img width="434" alt="image" src="https://user-images.githubusercontent.com/100017195/224199610-aa80410f-3a18-43c0-a857-e561bf0ecdc2.png">
