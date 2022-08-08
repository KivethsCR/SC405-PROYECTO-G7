from selenium import webdriver
from selenium.webdriver.support.ui import Select
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
import time
from keyboard import press


#########################################################################################################
#########################################################################################################
##################################Prueba de Adming Log in Exitosa########################################
#########################################################################################################
#########################################################################################################
username = "admin"
password = "admin"
driver = webdriver.Chrome(executable_path=r"C:\cdriver\chromedriver.exe")
driver.get("http://localhost/bankoint-master/administrator")
driver.find_element(By.NAME,"username").send_keys(username)
driver.find_element(By.NAME,"password").send_keys(password)
driver.find_element(By.XPATH, "//*[@id='layoutAuthentication_content']/main/div/div/div/div/div[2]/form/div[3]/button").click()
print("logged in succesfully")
time.sleep (2)
#########################################################################################################
#########################################################################################################
#############################Prueba de Adming Log in Contraseña incorrecta###############################
###########A#############################################################################################
#########################################################################################################
username = "admin"
password = "1234"
url = "http://localhost/bankoint-master/master"
driver = webdriver.Chrome(executable_path=r"C:\cdriver\chromedriver.exe")
driver.get("http://localhost/bankoint-master/administrator")
driver.find_element(By.NAME,"username").send_keys(username)
driver.find_element(By.NAME,"password").send_keys(password)
driver.find_element(By.XPATH, "//*[@id='layoutAuthentication_content']/main/div/div/div/div/div[2]/form/div[3]/button").click()
print("logged in succesfully")
time.sleep (4)
#########################################################################################################
#########################################################################################################
#############################Prueba de Adming Log in Usuario incorrecto##################################
#########################################################################################################
#########################################################################################################
username = "juan"
password = "1234"
url = "http://localhost/bankoint-master/master"
driver = webdriver.Chrome(executable_path=r"C:\cdriver\chromedriver.exe")
driver.get("http://localhost/bankoint-master/administrator")
driver.find_element(By.NAME,"username").send_keys(username)
driver.find_element(By.NAME,"password").send_keys(password)
driver.find_element(By.XPATH, "//*[@id='layoutAuthentication_content']/main/div/div/div/div/div[2]/form/div[3]/button").click()
print("logged in succesfully")
time.sleep (4)
#########################################################################################################
#########################################################################################################
#############################################Prueba de deposito##########################################
#########################################################################################################
#########################################################################################################
driver.find_element("link text", "NUEVO DEPOSITO").click()
descr = "Deposito de prueba 1"
monto= 1000
OptionValue= Select(driver.find_element(By.NAME,"person_id"))
OptionValue.select_by_value("4")
driver.find_element(By.ID,"description").send_keys(descr)
driver.find_element(By.ID,"amount").send_keys(monto)
driver.find_element(By.CSS_SELECTOR,"div button").click()
time.sleep(2)
press('enter')
#########################################################################################################
#########################################################################################################
########################################Prueba de deposito negativo######################################
#########################################################################################################
#########################################################################################################
driver.find_element("link text", "NUEVO DEPOSITO").click()
descr = "Deposito negativo"
monto= -5000
OptionValue= Select(driver.find_element(By.NAME,"person_id"))
OptionValue.select_by_value("4")
driver.find_element(By.ID,"description").send_keys(descr)
driver.find_element(By.ID,"amount").send_keys(monto)
driver.find_element(By.CSS_SELECTOR,"div button").click()
