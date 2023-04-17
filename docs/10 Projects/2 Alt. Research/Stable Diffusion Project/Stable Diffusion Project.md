---
aliases:
type: project
project: sd
status: open
priority: p4
creationtag: 2022-11-01 16:32
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"sd")
OR contains(file.tags,"SD") 
OR contains(infotags,"SD") 
GROUP BY type
SORT file.ctime asc 
```
# Resources
- [The StableDiffusion saubreddit](https://www.reddit.com/r/StableDiffusion/top/?sort=top&t=month#res:ner-page=2)
- See also their discord
- Maybe I also saved some stuff on github
- The Automatic1111 SD webui for easy interaction with SD 
	- https://github.com/AUTOMATIC1111/stable-diffusion-webui
# Statement
The goal of this project is to be able to generate or at least experiment with image generation using available Stable Diffusion methods.

# Log
## [[26.01.23]]
I don’t have a clear how to in order to restore my previous set up
Going to take a look at my saved repos and see if I can move that over to this machine

### AUTOMATIC1111 Git Repo
- https://github.com/AUTOMATIC1111/stable-diffusion-webui
Stable Diffusion Webui
A great place to start
Still requires some knowledge of python
A good place to start is here:
- https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features
- They provide a very good direction from here
- Start with the SD2 checkpoint model from Hugging Face
	- https://huggingface.co/stabilityai/stable-diffusion-2
	- 
Also provide several extensions
- https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions
- https://github.com/d8ahazard/sd_dreambooth_extension




# Look at saved reddit threads to see if you can get that stable diffusion thing up and going
- [Download the improved 1.5 model with much better faces using the latest improved autoencoder from stability, no more weird eyes : StableDiffusion](https://www.reddit.com/r/StableDiffusion/comments/ya21at/download_the_improved_15_model_with_much_better/)
- [GitHub - TheLastBen/fast-stable-diffusion: fast-stable-diffusion, +25-50% speed increase + memory efficient + DreamBooth](https://github.com/TheLastBen/fast-stable-diffusion)
>  1- Open the AUT1111 Colab in this repo : [https://github.com/TheLastBen/fast-stable-diffusion](https://github.com/TheLastBen/fast-stable-diffusion)
> 
> 2- Run the first 3 cells.
> 
> 3- In your gdrive, download "sd/stable-diffusion-webui/models/Stable-Diffusion/model.ckpt"
> 
> example :
> 
> Old vae : [https://imgur.com/nVZhnwf](https://imgur.com/nVZhnwf)
> 
> New vae : [https://imgur.com/h5o7Ie4](https://imgur.com/h5o7Ie4)
> 
> The process was to download the diffusers model from the [https://huggingface.co/runwayml/stable-diffusion-v1-5](https://huggingface.co/runwayml/stable-diffusion-v1-5) then the new autoencoder from [https://huggingface.co/stabilityai/sd-vae-ft-mse](https://huggingface.co/stabilityai/sd-vae-ft-mse), replace the vae in the 1.5 model and convert everything to a ckpt.
> 
> The Dreambooth from the repo also uses the latest autoencoder