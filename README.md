# Datathon_DG5
Datathon2025_Team5

# set up checks in your terminal
python3 --version
python3 -m ensure pip --upgrade
pip3 --version
pip3 install snowflake-connector-python
pip3 show snowflake-connector-python
# install snowflake-sqlalchemy if you are using SQLAlchemy and snowpark
pip3 install snowflake-sqlalchemy
pip3 install snowflake-snowpark-python
# using snowflake connector
from snowflake.snowpark import Session
# Create a session
session = Session.builder.configs({
    'user': 'YOUR_USERNAME',
    'password': 'YOUR_PASSWORD',
    'account': 'YOUR_ACCOUNT',
    'warehouse': 'YOUR_WAREHOUSE',
    'database': 'YOUR_DATABASE',
    'schema': 'YOUR_SCHEMA'
}).create()
# Example: Create a DataFrame
df = session.read.option("header", "true").csv("s3://your-bucket/your-file.csv")
# Perform some operations
df.show()
