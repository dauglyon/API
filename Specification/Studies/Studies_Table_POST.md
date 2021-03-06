### Save study Observation Units as table [POST /brapi/v1/studies/{studyDbId}/table]

Images can optionally be saved using this call by providing a zipped file of all images in the datafiles. The physical zipped file should be transferred as well in the mulit-part form data.

Scope: PHENOTYPING

+ Parameters
    + studyDbId (required, string, `1`) ... Identifier of the study. Usually a number, could be alphanumeric.
    
+ Request
    
        {
            "metadata": {
                "pagination" : { 
                    "pageSize":20, 
                    "currentPage":0, 
                    "totalCount":2, 
                    "totalPages":1 
                },
                "status" : [],
                "datafiles": [ "all_images.zip" ]
            },
            "result" : {
                "headerRow": [ "observationUnitDbId", "collector", "observationTimestamp", "variable1Id", "variable2Id", "variable3Id" ],
                "observationVariableDbIds": [ "variable1DbId", "variable2DbId", "variable3DbId", "imagevariable1DbId" ],
                "data" :
                [
                    [1, "Mr. Technician1", "2015-06-16T10:00:00Z", "variable1Value", "variable2Value", "variable3Value", "image1.jpg" ],
                    [2, "Mr. Technician2", "2015-06-16T11:00:01Z", "variable1Value", "variable2Value", "variable3Value", "image2.jpg" ]
                ]
            }
        }
        
+ Response 200

