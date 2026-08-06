Steps Before sending to Zev:

1. Hebrew documentation where possible - more its better
2. OCR:

    a. DO short research over Python OCR options and describe why we select specific model
    b. Create notebook that take open source OCR model and extract text 
    from the images in dataset_images dir for 8 angles by routing the image 8 times 45 degrees
    c. Output to DF with 8 texts per image.
3. REGEX:

    a. DO short research and collect small DB of passport string patterns.
    b. Transform the DB to regex.
    c. Read OCR outputs and try to find passports by some rating to how many regexes matched. 
4. Crate description of future DNN model for passports recognition.

