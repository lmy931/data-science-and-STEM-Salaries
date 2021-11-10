# Data science and STEM Salaries

This jupyter notebook performs exploratory data analysis(EDA) on 62,000 salary records from top global companies. 


## Prerequisites

pip install -r requirements.txt


## About Dataset

**Context**

62,000 salary records from top companies. This data was scraped off levels.fyi and then I cleaned it up a tad.

**Content**

This dataset contains useful information such as education level, compensation (base salary, bonus, stock grants), race, and more.

**Acknowledgements**

This dataset uses the technique in this article to get the data, but uses a different cleaning techniques.

https://towardsdatascience.com/a-beginners-guide-to-grabbing-and-analyzing-salary-data-in-python-e8c60eab186e


## Relationship with education


![image](data:image/png;base64,<data:image/png;base64,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HQAAAPAgBHQPdOjQIQ0dOrRK2/PPP69XXnmlxn3WrFmjhIQEd5cGN+ncubOGDx+uoUOHatKkSTp58mS1r4NTpk+frsjISN18880aNGiQpk2bJrvdfoGr9hxXXXWV4uPjnT+XlZWpX79+uv/++8/6WAUFBXrzzTfPqY7IyEiXt22qfXjqtX7zzTdrxIgR+uyzz87pONOnT9d77713Vvv06tXrrO/nbPr0rrvu0qBBgzRs2DANHjxYCQkJKigoOOv7bCxefPFFxcTEaNiwYRo+fLi++OKLC3bfx48f1+zZszVw4EDFxMTozjvvPOP9n3p91Pbei0r/+7v0ywzy1ltvae3atbXuXxeZZefOnef0Hl+du+66S19++WWdHKuuNOqTRIGGonnz5lq3bp0k6ZFHHtHbb7+tqKioWveZNm2aBg8eLGOMVqxYobvvvlv//Oc/5evreyFK9igtWrTQf/7zHxUXF6t58+b68MMPFRISck7HKigo0FtvvaU777zT5X2MMTVebKI27urDsrIy+fh45tv7L1/r27dv14IFC/T3v/+9nqs6XXl5uby9vc96v6SkJHXr1k0Oh0MLFizQhAkT6uTxeXKfVufzzz/X+++/r5SUFPn6+io3N9d5vZELYdasWbr00ku1adMmeXl5KSsrS999990Fu/+m7Pbbb6/vEhqFhvPbDkmVn/K6d++unTt3qrCwUI8//riuu+66Ktu8//77evHFF/Xiiy/q6aefVkBAgDIyMvTzzz8rPj7eGQiefvppbd++XRaLRePHj9eQIUM0d+5c3XDDDRowYIAmTpyowMBAzZ8/X8nJyTp06JBGjRql++67T71799bnn3+ukJAQvfDCC7UuFYSzc9111+nbb7+VVBkSZs2aVetzbbFYNHr0aG3evFnbtm3TwIED66PsehcREaH3339fgwcPVmpqqmJiYrR7925J0t69e/XEE084A/wTTzyhDh066D//+Y9mzJih0tJSVVRU6Pnnn9eiRYt08OBBDR8+XL/97W/16KOPavny5dqwYYMcDoeioqI0adIkHTp0SPfdd5/69u2rPXv26K9//atatWolSTpx4oQmT56s7OxsVVRUaMKECRoyZEiNtVfXh+np6Xr++eflcDjUrl07zZ8/X/7+/vrggw80f/58tWrVSl26dFFWVpaWLl2q559/Xjk5OTp8+LBatWqlmTNnas6cOfrpp58kSX/+85/Vu3dvnThxQo899pj279+v8vJyPfjgg/X2mikqKlJgYKCkyhHPCRMmqKCgQGVlZXrooYecda1du1avvPKKLBaLrrrqKj3zzDOSpE8//VSvvfZalfc2SdX21y/V9P63c+dOLVmyRFarVfv27dO//vUvZ5/m5ORoypQpKioqUnl5uebOnXvae+8v+fr6Kj4+XlFRUfrmm2909dVXa926dXrjjTdUWlqqHj16aM6cOfL29lZycrKWL18uq9Wq9u3by9fXV7Nnz9b06dMVFBSkr7/+Wl26dNEdd9yhefPm6dixY2revLkee+wxdezYUbm5udX2dX36+eef1apVK+eHzdatWztv27Fjh5566imVl5era9eumjdvnnx9fRUZGamhQ4dq586dKi0t1WOPPaYFCxboxx9/1NixY53B70z9e/DgQX3xxRdKSkqSl1flRIF27dqpXbt2kqS//e1vWr16tSQpLi5Oo0ePrvFxlJeXKykpSbt27ZLD4dCdd96p3//+96qoqFBCQoI++eQTXXrppaqoqNAtt9yiwYMHKyMjQ08++aROnDihVq1aaf78+TVeg6Uxev7559WiRQuNHTtWe/fu1cyZM9WiRQtde+212r59u9avXy+p8ndq7NixysrK0sCBAzVt2jSVl5dr5syZysjIkMVi0S233KLRo0frxx9/1Jw5c5Sbmytvb28tWrRIUuV77aRJk7R//3516dJFSUlJslgsNb7Gamr3SAYeJysry8TExFRpW7x4sVm+fLn5wx/+YObPn2+MMeb9998399xzjzHGmNWrV5t58+aZTZs2mdtvv93k5eUZY4x59NFHzZ/+9CdTXl5u/vOf/5iBAwcaY4x57733zOjRo01ZWZn5+eefTf/+/Y3dbjfr1683Tz75pDHGmFtuucWMGjXKGGPM9OnTzbZt20xWVpbp3Lmz+frrr40xxkyaNMmsXbvW7c9JY9ezZ09jjDGlpaXmgQceMG+++Watz/Wjjz5qNmzYUOUYiYmJZunSpRe2cA/Rs2dPs2/fPvOnP/3JFBcXm5tvvtl8/PHHZty4ccYYYwoLC01paakxxpgPP/zQPPjgg8YYYxISEsy6deuMMcaUlJSYkydPnvb7t337djNr1ixTUVFhysvLzbhx48yuXbtMVlaWueqqq8znn39+Wj3vvfeemTlzpvPngoKC07aprQ+PHj1q7rjjDnP8+HFjjDFLly41zz//vCkuLjYRERHm4MGDxhhjpkyZ4nyMixcvNiNGjDAnT540xhjz8MMPm08++cQYY8zhw4fN4MGDjTHGPPvss87XUX5+vomOjnbez4Vw9dVXm5tvvtkMGjTIXHvttebLL780xlS+9gsLC40xxhw9etQMHDjQVFRUmP3795vo6Ghz9OhRY4wxx44dM8bU/N5WU38Z8/9/z2p6//v4449Njx49nM/vL73yyivmhRdeMMYYU1ZW5qz1l/7whz+YvXv3VmkbP368SU1NNQcOHDD333+/cTgcxhhj5syZY1JSUkx2dra58cYbzbFjx4zD4TC33367mTdvnvMxjhs3zpSVlRljjLn77rvNDz/8YIwxZs+ePeauu+4yxtTc1/WpqKjI3HzzzSY6OtrMmTPH7Ny50xhjnK/h77//3hhjTHx8vPnb3/5mjDHmxhtvNG+++aYxxpjHH3/cDB061BQWFpqjR4+afv36GWNq799TtmzZYiZMmFBtXV9++aUZOnSoOX78uCkqKjJDhgwxX331lTHm/78+fvke8Pbbb5u//vWvxpjK94gRI0aYgwcPmg0bNph7773XlJeXm5ycHHPdddeZDRs2GIfDYW677Tbn6zU1NdVMnz69Tp5TT3Lq9/jUf/3793e+bk/lFWOMiYmJMbt37zbGGPPMM884n9fVq1ebyMhIU1BQYIqLi83vfvc789NPP5kvv/zSjB492nk/+fn5xhhj4uLizKZNm4wxla+hEydOmI8//thce+215siRI6a8vNzceuut5pNPPqnxNVbba6+63936xgi6B6rpSqan2k9NfejSpYsOHz7svH3nzp3KyMjQq6++qoCAAGf7wIED5eXlpSuuuEL//e9/JUm7d+9WTEyMvL299atf/Up9+vTRl19+qeuuu04rVqzQgQMHdMUVVyg/P185OTn6/PPPNXPmTOXl5enSSy9V586dq60B56a4uFjDhw+XVDmCHhcXp5ycnLN6rk0TXzH16quv1qFDh7R+/Xr179+/ym2FhYV69NFH9eOPP8pisTi/au/Zs6deeuklZWdnKzo6Wpdddtlpx/3www/14YcfKjY2VlLliE1mZqbatm2rX//61+rZs+dp+1x55ZV66qmn9Mwzz+jGG2+sdaT1l0714RdffKEDBw44RwxLS0vVs2dPff/991VGAmNiYrRy5Urn/pGRkc5vWD766CMdOHDAeVtRUZGKioqUnp6urVu36tVXX5UklZSU6MiRI+rYsaNLNZ6vX05x+fzzz/Xoo49q/fr1MsZowYIF+uSTT+Tl5SW73a7//ve/+vjjjzV48GDnCGxwcLDzWNW9t9XUX3369HHuV9P7X0BAgLp16+Z8fn+pW7du+vOf/6yysjINHDjQ+Xt5Jqf6dMeOHcrIyFBcXJykyt/5Nm3aKCAgQH369HE+rsGDByszM9O5/+DBg+Xt7a3jx4/r888/10MPPeS8zeFwSKq5r3/5d+BC8/f315o1a/Tpp59q586dmjJlih555BFdc801uvTSS3X55ZdLkkaMGKE333zTOYo9YMAASZW/QydOnHA+Bj8/PxUUFLjUv7XZvXu3Bg4cqBYtWkiq/Hv66aef6pprrql2+w8//FDffvutNm7cKKnyveTHH3/U7t27NXjwYHl5eeniiy9W3759JUk//PCD9u/frzFjxkiSKioqdPHFF5/ls+f5fvl7LFXOKc/IyKiyTUFBgY4fP65rr71WkjR06FC9//77zttDQ0OdF4js2LGjDh8+rE6dOikrK0uPPfaY+vfvr/DwcBUVFclutzuzj5+fn/MY3bt3l81mk1T5N+Dw4cMKCAio9jXWr1+/Wl97noaA7oGCg4OVn59fpS0/P1+XXnqpJDm/jvHy8lJ5eblzm3bt2ikrK0s//PCDunXr5myv7uubmsJcSEiI8vPztX37dl133XXKz8/Xhg0b1KJFCwUEBCgvL6/K8by9vVVSUnLuDxaSTn+zO+Vsnut9+/YpNDTULfU1FJGRkXr66af1+uuvKy8vz9m+aNEi9e3bV3/961916NAh3X333ZKkYcOGqUePHnr//fc1duxYJSYmnhbOjDEaN26cfv/731dpP3TokPOP/P+6/PLLtWbNGn3wwQd69tlnFRYWpgcffPCM9Z/qQ2OMwsLCtGDBgiq3f/3117Xuf9FFFzn/XVFRoXfeeafa6WeLFy9Whw4dzliPu/Xq1UvHjh1Tbm6uPvjgA+Xm5mrNmjVq1qyZIiMjVVJSUusHz5re26rrr//dpiY19WmfPn3097//XR988IGmTZumsWPHOkNiTcrLy7V//3516NBBR48e1YgRI/TII49U2Wbz5s21HuNUnxpjFBgYWO37RG19XZ+8vb3Vt29f9e3bV1deeaXWrl17xg82zZo1k1T59+2X/evl5aWysjKX+rdTp0765ptvVFFR4ZzicsrZDmQYYzRr1izdcMMNVdp/GTT/d/tOnTrpnXfeOav7aYzO9Fz/79+38vJyBQUFad26dUpPT9c//vEPbdiwQTNnzjyrY9R0vw1tEItVXDyQv7+/Lr74Yu3YsUOSlJeXp+3bt59xTuGvf/1rPf/883r00Uf1n//8p9Zt+/Tpow0bNqi8vFy5ubn69NNP1b17d0mVfzRXrFihPn366LrrrtOrr77q8gggLjxjjF5//XX9/PPPp/0RaWri4uI0YcIEXXXVVVXaCwsLnSeNpqSkONuzsrLUrl073X333YqMjNS3334rf39/HT9+3LlNeHi4Vq9e7Wyz2+06evRorXXY7XZddNFFGj58uMaOHXvGYP2/fdizZ0999tln+vHHHyVJJ0+e1A8//KAOHTooKytLhw4dkiT961//qvGY4eHhVU5O3LdvX5X2U3+szlSbO3333XcqLy9XcHCwCgsL1aZNGzVr1kwff/yx89ui0NBQvffeezp27JgkVfngVR1X+qu297+aHD58WG3atNGtt96qW265RV999VWt25eWlurZZ59V27ZtdfXVVys0NFQbN2501pKXl6fDhw+re/fu+uSTT5Sfn6+ysjJt2rSp2uOdGhXcsGGDpMrXzDfffON8zNX1dX36/vvvq3wTsG/fPv36179Whw4ddPjwYedre926dS6Pfkuu9e9vfvMbde3aVYsXL3a+zjMzM7Vlyxb16dNHW7Zs0cmTJ3XixAlt2bKl1r9v4eHheuutt5zfuv3www86ceKEevfurU2bNqmiokL//e9/tWvXLkmVH85zc3P1+eefS6p8HZzp73FjFRQUJH9/f+3Zs0dS7e9Xp+Tm5soYo0GDBumhhx7S119/rYCAANlsNm3ZskVS5TdHJ0+erPEYNb3Gzve1d6Exgu6hnn76ac2bN09PPvmkJGnixIn6zW9+c8b9OnTooKSkJD300EN66aWXatwuKipKn3/+uYYPHy6LxaL4+Hjn13C9e/dWenq62rdvr1//+tfKz88noHugp59+Wi+88IKKi4vVo0cPvf766557sssFYrPZdM8995zWfu+992r69On629/+pn79+jnb//Wvf+ndd9+Vj4+PfvWrX2nixIkKDg7Wtddeq6FDh+qGG27Qo48+qu+++845YteiRQs988wzp43M/dL+/fv19NNPy8vLSz4+Ppo7d26129XUh61bt9b8+fP18MMPO6cxTJ48WZdffrnmzJmje++9V61atao1VM6cOVMJCQkaNmyYysvLdd111ykhIUETJkzQE088oZtvvlnGGF1yySVaunSpK09vnfjldC5jjJ566il5e3tr2LBhGj9+vEaOHKnOnTs7R/g7deqkBx54QHfddZe8vLx0zTXXON8XqxMeHl5tf7Vp08a5TU3vf99//32Nx921a5deeeUV+fj4qEWLFnrqqaeq3W7q1Kny9fWVw+HQb3/7W73wwguSpCuuuEKTJ0/WH//4R1VUVKhZs2aaPXu2evbsqfvvv1+33nqrrFarOnbs6Pza/38988wzmjt3rl588UWVlZVpyJAhuvrqq2vs6/p04sQJJSYmqqCgQN7e3mrfvr0SEhLk5+en+fPn66GHHnKeqHc2q3640r+S9Pjjj+vJJ59UVFSULrroIgUHBys+Pl5dunTRyJEjNWrUKEmVH+prmt4iSaNGjdLhw4c1cuRIGWPUqlUrvfDCCxo0aJB27NihoUOH6rLLLlP37t3VsmVL+fr6avHixUpMTFRhYaHKy8t1zz33qFOnTufwLDZ8jz/+uGbNmqUWLVro+uuvP+O0q5ycHM2YMUMVFRWSpIcfflhS5Xvl7NmztWjRIjVr1sx5kmh1anqN+fr6ntdr70KzmIY25g8ATdjx48fl7+8vY4zmzZunyy67zGPnUMI1p/q0rKxMDz74oG655ZYzLrOK+neq344dO6ZRo0bprbfeapTzzc/HqedIkpYtW6acnBzNmjWrnqtqGBhBB4AGJDk5WSkpKSotLVXnzp1122231XdJOE9LlizRRx99pJKSEoWHhzfZpVIbmgceeEAFBQUqLS3VhAkTCOfV+OCDD7R06VKVl5fr17/+da3ffqEqRtABAAAAD8JJogAAAIAHIaADAAAAHoSADgAAAHgQAjoANFKRkZEaPHiwhg8f7vzv1Brqv3TVVVdVWfu9rhw6dOi0C7bcd999OnjwYJ3fFwA0JqziAgCN2OLFi3XllVfWy30fPnxY77zzTpWVZl5++eV6qQUAGhJG0AGgidm0aZMGDx6s3//+984L6UiVI959+/at8ed///vfGjlypG6++WbFxsY6r2T5yCOPaOTIkRo2bJgmTpyo/Px8SVJCQoK+++47DR8+XJMmTZJUOaq/f/9+SdKPP/6oe+65R8OGDdOIESO0bds2531dddVVeumll3TLLbdowIAB2rhxo/ueEADwMIygA0AjNmnSJPn5+UmSvL299fLLL+svf/mL3nrrLXXo0MHlEe0ffvhBs2bN0ptvvqnLLrtMDofDeZXTmTNnqnXr1pKkhQsX6uWXX9bUqVM1e/ZsPfXUU1qzZk21x5w6dapuvfVWjRo1SgcOHNCdd96pDRs2OI8VEBCg1atXa/fu3Zo8ebIGDRp0vk8HADQIBHQAaMT+d4pLWlqarrnmGnXo0EGSdNtttykpKemMx/noo48UERGhyy67TJLk6+srX19fSdK6dev0z3/+U6WlpTpx4oRzm9oUFRVp3759uuWWWyRJV1xxhTp37qw9e/YoMjJSkjRkyBBJUs+ePZWTk6OSkhLnhw0AaMwI6ADQhNR2bTofH58qt5eUlJxxv08//VRvvfWW3n77bbVu3Vr//Oc/tXLlynOuz2KxOP/9y5F/SSorKyOgA2gSmIMOAE1Ir1699PXXXyszM1OSlJyc7LztV7/6lUpLS/Xjjz9KktavX++8LTw8XNu2bXPu53A4VFRUpIKCAgUEBCg4OFgOh0OrV6927hMQEKCioqJq6wgICFDnzp2VkpIiSfruu+/0zTffqEePHnX5cAGgQWIEHQAasV/OQZekxMREPfbYY3rggQcUHByswYMHO2/z8fHRzJkzNWbMGF1yySVVThC97LLL9Nhjj2nKlCkqLy+Xt7e3nnzySUVEROjdd9/VTTfdpJCQEHXt2lVffvmlpMoTPS+//HINHTpUHTp00OLFi6vUlpSUpNmzZ+u1116Tj4+Pnn76aef8cwBoyiymtu87AQAAAFxQTHEBAAAAPAgBHQAAAPAgBHQAAADAgxDQAQAAAA9CQAcAAAA8CAEdAAAA8CAEdAAAAMCDENABAAAAD/L/ANNaYOQ8Lup6AAAAAElFTkSuQmCC%0A>)

