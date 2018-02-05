# sp
finding the hq


filename <- read.csv("C:/Users/Sanchit Pereira/Desktop/company.csv")
filename$website <- paste0("www.",filename$CUSTOMER,".com")
url.exists(filename$website[1])
?url.exists()
install.packages("RCurl", dependedncies = TRUE)
library("RCurl")
?url.exists()

for(i in 1:1611){
  if(url.exists(filename$website[1])== TRUE){
    filename$value[i] <- "valid"
  }else{
    filename$value[i] <- "invalid"
  }
}

for(i in 1:1611){
url <- filename$website[i]
html <- getURLContent(url)

if(html == ""){
  filename$value[i] <- "failure"
}else{
  filename$value[i] <- "success"
}
}
url.exists(filename$website)

invalid <- filename[filename$value == "invalid",]
hey <- filename[filename$CUSTOMER == "Grand Total",]
hey <- NULL




