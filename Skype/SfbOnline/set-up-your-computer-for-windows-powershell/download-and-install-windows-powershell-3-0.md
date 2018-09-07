---
title: Télécharger et installer Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Télécharger, installer et utiliser Windows PowerShell 3.0 pour créer une session PowerShell distante se connectant à Skype Entreprise Online.
ms.openlocfilehash: 8470a095e516179d1d328f47c1fe10d5a9e00aa6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862884"
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="08d0d-103">Télécharger et installer Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="08d0d-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="08d0d-104">Si vous utilisez Windows 8.1, Windows 8 Windows Server 2012 R2 ou Windows erver 2012, vous disposez normalement déjà de Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="08d0d-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="08d0d-105">Cette application est en effet pré-installée sur ces systèmes d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="08d0d-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="08d0d-106">Si vous utilisez Windows 7 ou Windows Server 2008 R2, il est également possible que vous utilisiez déjà Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="08d0d-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="08d0d-107">La possibilité existe cependant que vous utilisiez la version 2.0 – laquelle était initialement livrée avec ces systèmes d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="08d0d-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="08d0d-108">Pour déterminer la version de Microsoft PowerShell que vous utilisez, effectuez les opérations suivante sur votre ordinateur Windows 7 ou Windows Server 2008 R2 :</span><span class="sxs-lookup"><span data-stu-id="08d0d-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="08d0d-109">Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell** et enfin sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="08d0d-110">Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="08d0d-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="08d0d-111">Des informations similaires à celles-présentées ci-dessous doivent s'afficher dans la fenêtre de console :</span><span class="sxs-lookup"><span data-stu-id="08d0d-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    <span data-ttu-id="08d0d-112">Si le numéro de version renvoyé est 3.0, c'est que vous utilisez Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="08d0d-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="08d0d-113">Si le numéro de version renvoyé n'est pas 3.0, vous devez installer Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="08d0d-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="08d0d-114">Vous pouvez télécharger Windows Management Frameworks 3.0, qui inclut Windows PowerShell 3.0, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="08d0d-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="08d0d-115">Une fois que vous avez vérifié que Windows PowerShell 3.0 est bien installé, vous devez vous assurer que PowerShell ait bien été configuré pour l'exécution de scripts distants.</span><span class="sxs-lookup"><span data-stu-id="08d0d-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="08d0d-116">Pour cela, démarrez PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="08d0d-117">Sous Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="08d0d-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="08d0d-118">Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="08d0d-119">Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="08d0d-120">Si vous utilisez Windows 8, effectuer la procédure suivante à la place :</span><span class="sxs-lookup"><span data-stu-id="08d0d-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="08d0d-121">Accédez à la barre des talismans, cliquez sur **Rechercher** puis faites un clic droit sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="08d0d-122">Vous pouvez accéder rapidement à la barre des talismans à partir de n'importe quel ordinateur Windows 8 (tactile ou non) en maintenant la touche Windows et en appuyant sur C.</span><span class="sxs-lookup"><span data-stu-id="08d0d-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="08d0d-123">Dans la barre d’outils située en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="08d0d-124">Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="08d0d-125">Après l'exécution de PowerShell, vous devez modifier la politique d'exécution pour permettre l'exécution de scripts distants.</span><span class="sxs-lookup"><span data-stu-id="08d0d-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="08d0d-126">Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="08d0d-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="08d0d-127">Lorsque vous exécutez la commande précédente, le message d'erreur suivant peut s'afficher : > *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span><span class="sxs-lookup"><span data-stu-id="08d0d-127">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="08d0d-128">En règle générale, ce message d’erreur s'affiche si vous n’exécutez pas PowerShell en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-128">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="08d0d-129">Fermez votre session PowerShell et démarrez une nouvelle session en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-129">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="08d0d-130">Pour vérifier que la politique d’exécution a été configurée correctement, saisissez l'expression suivante dans l’invite PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="08d0d-130">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="08d0d-131">Si vous obtenez la valeur suivante, c'est que tout a été configuré correctement :</span><span class="sxs-lookup"><span data-stu-id="08d0d-131">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="08d0d-132">Si vous n'utilisez pas Windows PowerShell 3.0, vous allez également devoir télécharger et installer Windows Management Frameworks 3.0 à partir du Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08d0d-132">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="08d0d-133">Il s’agit d’un package d’installation qui inclut Windows PowerShell 3.0 et Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="08d0d-133">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="08d0d-134">Ce package d’installation peut être nécessaire si vous utilisez Windows 7 et n’avez pas encore effectué la mise à jour vers Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="08d0d-134">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="08d0d-135">Si vous utilisez Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, aucune installation de Windows PowerShell 3.0 ne devrait être nécessaire.</span><span class="sxs-lookup"><span data-stu-id="08d0d-135">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="08d0d-136">Windows PowerShell 3.0 est en effet préinstallé sur ces systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="08d0d-136">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="08d0d-137">Avant d’installer Windows Management Framework 3.0 :</span><span class="sxs-lookup"><span data-stu-id="08d0d-137">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="08d0d-138">Assurez-vous d'avoir téléchargé la bonne version du package d’installation.</span><span class="sxs-lookup"><span data-stu-id="08d0d-138">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="08d0d-139">Si vous utilisez la version 64 bits de Windows 7, téléchargez le fichier Windows6.1-KB2506143-x64.msu.</span><span class="sxs-lookup"><span data-stu-id="08d0d-139">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="08d0d-140">Si vous utilisez la version 32 bits de Windows 7, téléchargez le fichier Windows6.1-KB2506143-x86.</span><span class="sxs-lookup"><span data-stu-id="08d0d-140">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="08d0d-141">Si vous utilisez Windows 7 sur votre ordinateur, assurez-vous d'avoir installé Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="08d0d-141">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="08d0d-142">Si vous n'êtes pas certain de la version de Windows que vous utilisez, ou si vous n'êtes pas sûr d'avoir installé Windows 7 Service Pack 1, cliquez sur **Démarrer**, faites un clic droit sur **Ordinateur** puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-142">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="08d0d-143">Ces informations seront mentionnées dans la boîte de dialogue Système.</span><span class="sxs-lookup"><span data-stu-id="08d0d-143">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="08d0d-144">Pour installer Windows Management Framework 3.0, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="08d0d-144">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="08d0d-145">Double-cliquez sur le fichier d’installation .MSU ( **Windows6.1-KB2506143-x64.msu** ou **Windows6.1-KB2506143-x86**).</span><span class="sxs-lookup"><span data-stu-id="08d0d-145">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="08d0d-146">Dans l'assistant Télécharger et installer des mises à jour, sur la page **Lire les termes du contrat de licence (1 sur 1)**, cliquez sur **J'accepte**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-146">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="08d0d-147">Une fois le processus d'installation terminé, cliquez sur **Redémarrer maintenant** pour redémarrer votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-147">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="08d0d-148">Après que l'ordinateur a redémarré, vérifiez que Windows PowerShell démarre correctement et que l'application soit bien exécutée en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-148">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="08d0d-149">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="08d0d-149">To do this:</span></span>
  
1. <span data-ttu-id="08d0d-150">Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="08d0d-150">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="08d0d-151">Si la boîte de dialogue Contrôle de compte d'utilisateur apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="08d0d-151">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="08d0d-152">Lorsque la console PowerShell s’affiche, vous devez vérifier que le service WinRM soit bien en cours d’exécution et qu’il ait été configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="08d0d-152">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="08d0d-153">Pour vérifier que le service est bien en cours d’exécution, saisissez la commande suivante dans l’invite PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="08d0d-153">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="08d0d-154">Des informations sur le service WinRM s'affichent alors à l’écran :</span><span class="sxs-lookup"><span data-stu-id="08d0d-154">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="08d0d-155">Si l'état du service n'est pas « En cours d'exécution », démarrez le service WinRM en saisissant la commande suivante, puis cliquez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="08d0d-155">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="08d0d-156">Une fois le service démarré, exécutez la commande suivante pour vous assurer que WinRM utilise une authentification de base :</span><span class="sxs-lookup"><span data-stu-id="08d0d-156">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="08d0d-157">Des informations similaires aux éléments suivants s'affichent alors à l’écran :</span><span class="sxs-lookup"><span data-stu-id="08d0d-157">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="08d0d-158">Si l’authentification de base a bien été définie sur true, vous êtes prêt à utiliser PowerShell pour une connexion à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="08d0d-158">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="08d0d-159">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="08d0d-159">Related topics</span></span>
[<span data-ttu-id="08d0d-160">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08d0d-160">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 