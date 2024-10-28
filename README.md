# qr-code-generator
A Python-based QR code generator that converts text or URLs into customizable QR codes.


import qrcode
from PIL import Image

def generate_qr_code(data, filename="qrcode.png", fill_color="black", back_color="white"):
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_H,
        box_size=10,
        border=4,
    )
    qr.add_data(data)
    qr.make(fit=True)

    img = qr.make_image(fill_color=fill_color, back_color=back_color)
    img.save(filename)
    print(f"QR code saved as {filename}")

# For website like pw skills
generate_qr_code("https://www.pwskills.com", filename="pwskills_qrcode.png")
