# NAICSjson

North American Industry Classification System encoded into JSON format
This file includes all 2012 NAICS industries, accurate to 5 or 6 digits.
Note: Please be advised that there are no gaurantees to its accuracy.


Using the following instructions, you will be able to implement a user-friendly method of inputting their NAICS code.

1. HTML Markup
 
			<select ng-options="ind.name for ind in MySectors " ng-model="naics.level1" required>
				 <option value="">Please Select</option>
			</select>
			
			<select ng-show="naics.level1" ng-options="ind.name for ind in naics.level1.subsectors" ng-model="naics.level2" required>
				 <option value="">Please Select</option>
			</select>
			
			<select ng-show="naics.level2" ng-options="ind.name for ind in naics.level2.subsectors" ng-model="naics.level3" >
				  <option value="">Please Select</option>
			</select>
			
			<select ng-show="naics.level3" ng-options="ind.name for ind in naics.level3.subsectors" ng-model="naics.level4">
				 <option value="">Please Select</option>
			</select>


2. Insert into your (angular) controller:

	    $http.get("path/to/subsectors.json").then(function(res){
                $scope.MySectors = res.data;
	     });

