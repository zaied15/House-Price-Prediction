import gradio as gr
import joblib

model = joblib.load("models/best_model.pkl")

def predict(
    income,
    age,
    rooms,
    bedrooms,
    population
):

    prediction = model.predict([
        [
            income,
            age,
            rooms,
            bedrooms,
            population
        ]
    ])

    return f"${prediction[0]:,.2f}"

demo = gr.Interface(
    fn=predict,
    inputs=[
        gr.Number(label="Average Area Income"),
        gr.Number(label="Average House Age"),
        gr.Number(label="Average Rooms"),
        gr.Number(label="Average Bedrooms"),
        gr.Number(label="Area Population")
    ],
    outputs="text",
    title="House Price Prediction",
    description="Predict USA house prices"
)

demo.launch(share=True)