# Mob Location by Entities Pie Chart
Suppose the player's coordinates when the mob first appears on the pie chart are $(x_1,z_1)$, the render distance is $R_1$; the player's coordinates when the mob appears the second time are $(x_2,z_2)$, the render distance is $R_2$, and the coordinates of the mob's location are $(x,z)$. Then $(x,z)$ can be calculated as follows:

$$ r_1=16R_1 \quad r_2=16R_2 $$

$$ \Delta x=x_2-x_1 \quad \Delta z=z_2-z_1 $$

$$ d=\sqrt{\Delta x^2+\Delta z^2} $$

$$ a=\frac{r_1^2-r_2^2+d^2}{2d} $$

$$ h=\sqrt{r_1^2-a^2} $$

$$ x=x_1+\frac{a\Delta x\pm h\Delta z}{d}\quad z=z_1+\frac{a\Delta z\mp h\Delta x}{d} $$

If $R_1=R_2=R$, i.e., without adjusting the render distance:

$$ r=16R $$

$$ \Delta x=x_2-x_1 \quad \Delta z=z_2-z_1 $$

$$ d=\sqrt{\Delta x^2+\Delta z^2} $$

$$ h=\sqrt{r^2-(\frac{d}{2})^2} $$

$$ x=\frac{x_1+x_2}{2}\pm\frac{h\Delta z}{d}\quad z=\frac{z_1+z_2}{2}\mp\frac{h\Delta x}{d} $$

If $d\ll r$, i.e., the distance between the two measurements is much smaller than the distance between you and the mob, keeping up to the second order, we can take the following approximation:

$$ x\approx\frac{x_1+x_2}{2}\pm(\frac{r}{d}-\frac{d}{8r})\Delta z\quad z\approx\frac{z_1+z_2}{2}\mp(\frac{r}{d}-\frac{d}{8r})\Delta x $$

Further approximation by ignoring the second-order term:

$$ x\approx\frac{x_1+x_2}{2}\pm\frac{r\Delta z}{d}\quad z\approx\frac{z_1+z_2}{2}\mp \frac{r\Delta x}{d} $$

That is:

$$ x\approx\frac{x_1+x_2}{2}\pm\frac{16R}{\sqrt{(\frac{x_1-x_2}{z_1-z_2})^2+1}}\quad z\approx\frac{z_1+z_2}{2}\mp \frac{16R}{\sqrt{(\frac{z_1-z_2}{x_1-x_2})^2+1}} $$

When using this formula for calculation, if $16R/d=10$, the order of magnitude of the error is about 1.
