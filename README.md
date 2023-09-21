# myrepo
Repository for testing my Git/GitHub setup
"A line I wrote on my local computer  " 
"This is a line from RStudio"
"I am Ivan Cheng and currently a 4th year student at UBC"
library(tidyverse)
library(janitor)
library(here)
n <- 20
ns <- 10000

means <- total_samples <- c()

for(i in 1:ns){
  samples <- 	rexp(n=n,rate = 4)
  total_samples <- append(total_samples, samples)
  means <- append(means, mean(samples))
}

hist(total_samples, breaks = 100)
hist(means, breaks = 100)
n <- 20
ns <- 10000

means <- total_samples <- c()

for(i in 1:ns){
  samples <- 	rlogis(n=n)
  total_samples <- append(total_samples, samples)
  means <- append(means, mean(samples))
}

hist(total_samples, breaks = 100)
hist(means, breaks = 100)
n <- 20
ns <- 10000

means <- total_samples <- c()

for(i in 1:ns){
  samples <- 	rcauchy(n=n, location = 0, scale = 1)
  total_samples <- append(total_samples, samples)
  means <- append(means, mean(samples))
}

hist(total_samples, breaks = 100)
hist(means, breaks = 100)
df <- read_csv("data/gusto.csv")
head(df,20)
tail(df)
dim(df)
df_subset <- select(df, day30:height)
df_subset_male <- filter(df_subset ,sex=="male")

df_subset_male_piping <- df %>% 
  select(day30:height) %>% 
  filter(sex=="male")