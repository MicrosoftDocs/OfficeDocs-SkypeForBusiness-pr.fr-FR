---
title: Télécharger et installer Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Télécharger, installer et utiliser Windows PowerShell 5.1 pour créer une session PowerShell distante se connectant à Skype Entreprise Online.
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701553"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="da80e-103">Télécharger et installer Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="da80e-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="da80e-104">Si vous utilisez la mise à jour anniversaire Windows 10 ou Windows Server 2016, vous utilisez déjà Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="da80e-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="da80e-105">En effet, cette application est préinstallée avec ces systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="da80e-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="da80e-106">Pour déterminer la version de Microsoft PowerShell que vous utilisez, effectuez les opérations suivante sur votre ordinateur Windows 7 ou Windows Server 2008 R2 ou Windows Server 2012 :</span><span class="sxs-lookup"><span data-stu-id="da80e-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="da80e-107">Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell** et enfin sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="da80e-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="da80e-108">Dans la console PowerShell, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="da80e-108">In the console window, type the following command and then press ENTER.</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="da80e-109">Des informations semblables à ce qui suit doivent être affichées dans la fenêtre de la console :</span><span class="sxs-lookup"><span data-stu-id="da80e-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="da80e-110">Si le numéro de version renvoyé est 5.1, c'est que vous utilisez Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="da80e-110">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="da80e-111">Si le numéro de version renvoyé n'est pas 5.1, vous devez installer Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="da80e-111">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="da80e-112">Vous pouvez télécharger Windows Management Framework 5.1, qui inclut Windows PowerShell 5.1, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="da80e-112">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="da80e-113">Une fois que vous avez vérifié que Windows PowerShell 5.1 est bien installé, vous devez vous assurer que PowerShell a bien été configuré pour l'exécution de scripts distants.</span><span class="sxs-lookup"><span data-stu-id="da80e-113">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="da80e-114">Pour cela, démarrez PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="da80e-115">Sous Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="da80e-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="da80e-116">Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="da80e-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="da80e-117">Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour confirmer que vous voulez exécuter PowerShell sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="da80e-118">Si vous utilisez Windows 8, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="da80e-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="da80e-119">Accédez à la barre des icônes, cliquez sur **Rechercher** puis faites un clic droit sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="da80e-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="da80e-120">Vous pouvez accéder rapidement à la barre des icônes sur un ordinateur Windows 8 (écran tactile ou normal) en maintenant la touche Windows enfoncée, puis en appuyant sur C.</span><span class="sxs-lookup"><span data-stu-id="da80e-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="da80e-121">Dans la barre d’outils située en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="da80e-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="da80e-122">Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="da80e-123">Après l'exécution de PowerShell, vous devez modifier la politique d'exécution pour permettre l'exécution de scripts distants.</span><span class="sxs-lookup"><span data-stu-id="da80e-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="da80e-124">Dans la console PowerShell, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="da80e-124">In the console window, type the following command and then press ENTER.</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="da80e-125">Lorsque vous exécutez la commande précédente, le message d'erreur suivant peut s'afficher : > *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span><span class="sxs-lookup"><span data-stu-id="da80e-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="da80e-126">En règle générale, ce message d’erreur s'affiche si vous n’exécutez pas PowerShell en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="da80e-127">Fermez votre session PowerShell et démarrez une nouvelle session en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="da80e-128">Pour vérifier que la politique d’exécution a été configurée correctement, saisissez l'expression suivante dans l’invite PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="da80e-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="da80e-129">Si vous obtenez la valeur suivante, tout est correctement configuré :</span><span class="sxs-lookup"><span data-stu-id="da80e-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="da80e-130">Si vous n'utilisez pas Windows PowerShell 5.1, vous allez également devoir télécharger et installer Windows Management Framework 5.1 à partir du Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da80e-130">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="da80e-131">Il s’agit d’un package d’installation qui inclut Windows PowerShell 5.1 et Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="da80e-131">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="da80e-132">Ce package d’installation peut être nécessaire si, par exemple, vous utilisez Windows 7 SP1 et n’avez pas encore effectué la mise à jour vers Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="da80e-132">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="da80e-133">Si vous utilisez Windows Server 2016 ou la mise à jour anniversaire Windows 10, il n’est pas nécessaire d’installer Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="da80e-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="da80e-134">Windows PowerShell 5.1 est en effet préinstallé sur ces systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="da80e-134">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="da80e-135">Avant d’installer Windows Management Framework 5.1 :</span><span class="sxs-lookup"><span data-stu-id="da80e-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="da80e-136">Vérifiez que vous avez téléchargé la version correcte du package d’installation.</span><span class="sxs-lookup"><span data-stu-id="da80e-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="da80e-137">Si vous utilisez la version 64 bits de Windows 7 SP1, téléchargez le fichier Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="da80e-137">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="da80e-138">Si vous utilisez la version 32 bits de Windows 7, téléchargez le fichier Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="da80e-138">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="da80e-139">Si vous exécutez Windows 7 sur votre ordinateur, vérifiez que vous avez installé Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="da80e-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="da80e-140">Si vous n'êtes pas certain de la version de Windows que vous utilisez, ou si vous n'êtes pas sûr d'avoir installé Windows 7 Service Pack 1, cliquez sur **Démarrer**, faites un clic droit sur **Ordinateur** puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="da80e-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="da80e-141">Ces informations seront mentionnées dans la boîte de dialogue Système.</span><span class="sxs-lookup"><span data-stu-id="da80e-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="da80e-142">Pour installer Windows Management Framework 5.1, suivez la procédure décrite dans [Installer et configurer WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="da80e-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="da80e-143">Après que l'ordinateur a redémarré, vérifiez que Windows PowerShell démarre correctement et que l'application soit bien exécutée en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="da80e-144">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="da80e-144">To do this run:</span></span>
  
1. <span data-ttu-id="da80e-145">Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="da80e-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="da80e-146">Si la boîte de dialogue Contrôle de compte d'utilisateur apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="da80e-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="da80e-147">Lorsque la console PowerShell s’affiche, vous devez vérifier que le service WinRM soit bien en cours d’exécution et qu’il ait été configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="da80e-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="da80e-148">Pour vérifier que le service est bien en cours d’exécution, saisissez la commande suivante dans l’invite PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="da80e-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="da80e-149">Des informations sur le service WinRM sont affichées à l’écran :</span><span class="sxs-lookup"><span data-stu-id="da80e-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="da80e-150">Si l'état du service n'est pas « En cours d'exécution », démarrez le service WinRM en saisissant la commande suivante, puis cliquez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="da80e-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="da80e-151">Une fois le service démarré, exécutez la commande suivante pour vérifier que WinRM utilise l’authentification de base :</span><span class="sxs-lookup"><span data-stu-id="da80e-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="da80e-152">Des informations semblables à ce qui suit sont affichées à l’écran :</span><span class="sxs-lookup"><span data-stu-id="da80e-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="da80e-153">Si l’authentification de base a bien été définie sur true, vous êtes prêt à utiliser PowerShell pour une connexion à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="da80e-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="da80e-154">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="da80e-154">Related topics</span></span>
[<span data-ttu-id="da80e-155">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da80e-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
