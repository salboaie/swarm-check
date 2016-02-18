# swarm-check
Static code checks, logic facts checks and dynamic (data flow) checks for executable choreographies


#Functionalities

## Standard reports
Swarm-check takes a set of machine templates and a set of organisation types and create reports:
  - the list of swarms (specific phases, constructors) on which the checker doesn't have sufficient privacy metadata   
  - the list of private data types accessible for each organisation type
  - reports about possible attacks: eg combinations of organisation types that when compromised can de-anonymize private data

## Specifc privacy queries
Swarm-check UI can be used to interrogate other arbitrary properties about the private data 

# How it works

## Static checks
 
 
 
## Dynamic checks


## Transformation checks


## Ontological checks

Declare information about the ontological tags

        checker.tag(tagname, {
            identity:boolean,
            private:boolean,
            sensitivity:0-10,
            related:"list of tags"
            })


        checker.fact( usage(model("x"), organisation("Y")) )
        
        checker.if(usage(model(X), organisation(Y))).then(expose(model(X),organisation(Y)))
        checker.if(usage(model(X), organisation(Y)).and.parnet(  ).then(expose(model(X),organisation(Y)))

Possible example:

      firewall.tag("Social Security Number", {
          identity:true,
          private:true,
          sensitivity:5
          })

      firewall.tag("Birth Date", {
          identity:false,
          private:true,
          sensitivity:3
          })
Declare annotation for privacy ontologic tag

firewall.tag(objectType, field, tagName)
Example:

      firewall.tag("User", "SSN",   "Social Security Number");
      firewall.tag("User", "birthDate", "Birth Date");
Declare rules about use of combinations between identity, private fields and access zones. It is possbile to declare access zones and parent relations between resources and zones

      