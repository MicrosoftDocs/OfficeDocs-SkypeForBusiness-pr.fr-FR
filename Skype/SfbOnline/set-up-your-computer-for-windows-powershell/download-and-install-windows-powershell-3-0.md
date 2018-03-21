---
title: "Téléchargez et installez Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: "Télécharger, installer et Windows PowerShell 3.0 permet de créer une session PowerShell distante qui se connecte à Skype pour entreprise en ligne."
ms.openlocfilehash: 28f4db7492c233f5cfa16137d77ed8e0dc4a6572
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="f33ad-103">Téléchargez et installez Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f33ad-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="f33ad-104">Si vous utilisez Windows 8.1, Windows 8, Windows Server 2012 R2 ou Windows Server 2012, vous disposez déjà de Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f33ad-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="f33ad-105">C’est parce que cette application est préinstallée sur les systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="f33ad-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="f33ad-106">Si vous exécutez Windows 7 ou Windows Server 2008 R2, vous pouvez également exécuter Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f33ad-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="f33ad-107">Toutefois, il est également possible que vous utilisez peut-être version 2.0 à la place, la version initialement livrés avec ces systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="f33ad-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="f33ad-108">Pour déterminer la version de Microsoft PowerShelll que vous utilisez, procédez comme suit sur votre ordinateur Windows 7 ou Windows Server 2008 R2 :</span><span class="sxs-lookup"><span data-stu-id="f33ad-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="f33ad-109">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez sur **Windows PowerShell**, puis cliquez sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f33ad-110">Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f33ad-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="f33ad-111">Informations semblables au suivant doivent ensuite être affichées dans la fenêtre de console :</span><span class="sxs-lookup"><span data-stu-id="f33ad-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="f33ad-112">Si le numéro de Version renvoyé est 3.0, Windows PowerShell 3.0 sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="f33ad-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="f33ad-113">Si le numéro de Version retourné n’est pas 3.0, vous devez installer Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f33ad-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="f33ad-114">Vous pouvez télécharger Windows Management Framework 3.0, qui inclut Windows PowerShell 3.0, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="f33ad-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="f33ad-115">Après avoir vérifié que Windows PowerShell 3.0 est installé, il se peut que vous devez vous assurer que PowerShell a été configuré pour exécuter des scripts à distance.</span><span class="sxs-lookup"><span data-stu-id="f33ad-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="f33ad-116">Pour ce faire, démarrez PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f33ad-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="f33ad-117">Sur Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f33ad-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="f33ad-118">Cliquez sur **Démarrer**sur **Tous les programmes**, sur **Accessoires**et cliquez sur **Windows PowerShell**, cliquez sur **Windows PowerShell**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="f33ad-119">Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour vérifier que vous souhaitez exécuter PowerShell sous les informations d’identification de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f33ad-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="f33ad-120">Si vous exécutez Windows 8, effectuez cette procédure à la place :</span><span class="sxs-lookup"><span data-stu-id="f33ad-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="f33ad-121">Accéder à la barre d’icônes et cliquez sur **Rechercher**, puis cliquez sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="f33ad-122">Vous pouvez accéder rapidement à la barre d’icônes sur n’importe quel ordinateur Windows 8 (écran tactile ou écran tactile-non) en maintenant la touche Windows enfoncée et en appuyant sur la touche C.</span><span class="sxs-lookup"><span data-stu-id="f33ad-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="f33ad-123">Dans la barre d’outils en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="f33ad-124">Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour vérifier que vous souhaitez exécuter PowerShell sous les informations d’identification de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f33ad-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="f33ad-125">Après l’exécution de PowerShell, vous devez modifier la stratégie d’exécution afin de permettre l’exécution de scripts à distance.</span><span class="sxs-lookup"><span data-stu-id="f33ad-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="f33ad-126">Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f33ad-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
<span data-ttu-id="f33ad-127">Pour vérifier que la stratégie d’exécution a été configurée correctement, tapez la ligne suivante à l’invite de PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f33ad-127">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="f33ad-128">Si vous revenir la valeur suivante, puis tout ce qui a été configuré correctement :</span><span class="sxs-lookup"><span data-stu-id="f33ad-128">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="f33ad-129">Si vous n’exécutez pas actuellement Windows PowerShell 3.0, vous devez également télécharger et installer Windows Management Framework 3.0 à partir du Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="f33ad-129">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="f33ad-130">Il s’agit d’un package d’installation qui inclut Windows PowerShell 3.0 et Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="f33ad-130">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="f33ad-131">Ce package d’installation peut être requis si vous exécutez Windows 7 et n’avez pas encore mis à jour pour Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f33ad-131">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="f33ad-132">Si vous exécutez Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, il ne doit y avoir aucun nécessaire d’installer Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f33ad-132">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="f33ad-133">Windows PowerShell 3.0 est préinstallé sur les systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="f33ad-133">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="f33ad-134">Avant d’installer Windows Management Framework 3.0 :</span><span class="sxs-lookup"><span data-stu-id="f33ad-134">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="f33ad-135">Assurez-vous que vous avez téléchargé la bonne version du package d’installation.</span><span class="sxs-lookup"><span data-stu-id="f33ad-135">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="f33ad-136">Si vous exécutez la version 64 bits de Windows 7, téléchargez le fichier Windows6. 1-KB2506143-x 64.msu.</span><span class="sxs-lookup"><span data-stu-id="f33ad-136">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="f33ad-137">Si vous exécutez la version 32 bits de Windows 7, téléchargez le fichier Windows6. 1-KB2506143-x 86.msu.</span><span class="sxs-lookup"><span data-stu-id="f33ad-137">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="f33ad-138">Si vous exécutez Windows 7 sur votre ordinateur, assurez-vous que vous avez installé Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="f33ad-138">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="f33ad-139">Si vous ne savez pas quelle version de Windows vous exécutez, ou vous n’êtes pas sûr si vous avez installé Windows 7 Service Pack 1 et cliquez sur **Démarrer**, cliquez sur **ordinateur**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-139">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="f33ad-140">Ces informations seront signalées dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f33ad-140">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="f33ad-141">Pour installer Windows Management Framework 3.0, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f33ad-141">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="f33ad-142">Double-cliquez sur le. Fichier d’installation MSU ( **package Windows6. 1-KB2506143-x 64.msu** ou **package Windows6. 1-KB2506143-x 86.msu**).</span><span class="sxs-lookup"><span data-stu-id="f33ad-142">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="f33ad-143">Dans l’Assistant de téléchargement et installer les mises à jour, dans la page **lire ces termes de la licence (1 / 1)** , cliquez sur **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-143">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="f33ad-144">Lorsque l’installation est terminée, cliquez sur **Redémarrer maintenant** pour redémarrer votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f33ad-144">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="f33ad-145">Une fois que l’ordinateur a redémarré, vérifiez que Windows PowerShell peut démarrer et que l’application peut être exécutée avec les informations d’identification d’administration.</span><span class="sxs-lookup"><span data-stu-id="f33ad-145">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="f33ad-146">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="f33ad-146">To do this:</span></span>
  
1. <span data-ttu-id="f33ad-147">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez sur **Windows PowerShell**, avec le bouton droit de **Windows PowerShell** et puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f33ad-147">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="f33ad-148">Si le contrôle de compte d’utilisateur s’affiche, cliquez sur **Oui** pour vérifier que vous souhaitez exécuter PowerShell sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f33ad-148">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="f33ad-149">Lorsque la console PowerShell s’affiche, vous devez ensuite vérifier que le service WinRM est en cours d’exécution et qu’il a été configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="f33ad-149">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="f33ad-150">Pour vérifier que le service est en cours d’exécution, tapez la commande suivante à l’invite de PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f33ad-150">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="f33ad-151">Informations sur le service WinRM puis apparaîtra à l’écran :</span><span class="sxs-lookup"><span data-stu-id="f33ad-151">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="f33ad-152">Si le service d’état n’équivaut pas « Exécution », démarrez le service WinRM en tapant la commande suivante, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f33ad-152">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="f33ad-153">Une fois que le service a démarré, exécutez la commande suivante afin de vous assurer que WinRM est l’authentification de base :</span><span class="sxs-lookup"><span data-stu-id="f33ad-153">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="f33ad-154">Des informations semblables à ce qui suit seront affiche à l’écran :</span><span class="sxs-lookup"><span data-stu-id="f33ad-154">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="f33ad-155">Si l’authentification de base a été définie sur true, vous êtes prêt à utiliser PowerShell pour se connecter à Skype pour entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="f33ad-155">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="f33ad-156">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f33ad-156">Related topics</span></span>
[<span data-ttu-id="f33ad-157">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f33ad-157">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

## <a name="feedback"></a><span data-ttu-id="f33ad-158">Commentaires ?</span><span class="sxs-lookup"><span data-stu-id="f33ad-158">Feedback?</span></span>
<span data-ttu-id="f33ad-159">Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="f33ad-159">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>