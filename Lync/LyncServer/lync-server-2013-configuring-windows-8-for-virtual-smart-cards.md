---
title: 'Lync Server 2013 : configuration de Windows 8 pour les cartes à puce virtuelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8fe9fb9bcca80e7e84f19bdc484dc693b1ee68
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="f0cc6-102">Configuration de Windows 8 pour l’utilisation de cartes à puce virtuelles avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0cc6-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0cc6-103">_**Dernière modification de la rubrique :** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="f0cc6-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="f0cc6-104">L’un des facteurs à prendre en compte lors du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce est le coût de mise en œuvre.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="f0cc6-105">Windows 8 fournit un certain nombre de nouvelles fonctionnalités de sécurité et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="f0cc6-106">Pour les ordinateurs équipés d’un processeur de module de plateforme sécurisée (TPM) qui correspond à la version de spécification 1,2, les organisations peuvent désormais bénéficier des avantages de l’ouverture de session par carte à puce sans faire d’autres investissements sur le matériel.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="f0cc6-107">Pour plus d’informations, consultez la rubrique utilisation de cartes à puce [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)virtuelles avec Windows 8 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="f0cc6-108">Pour configurer Windows 8 pour les cartes à puce virtuelles</span><span class="sxs-lookup"><span data-stu-id="f0cc6-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="f0cc6-109">Connectez-vous à l’ordinateur Windows 8 à l’aide des informations d’identification d’un utilisateur à extension Lync.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="f0cc6-110">À l’écran d’accueil de Windows 8, déplacez votre curseur vers le coin inférieur droit de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="f0cc6-111">Sélectionnez l’option **Rechercher** , puis recherchez invite de **commandes**.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="f0cc6-112">Cliquez avec le bouton droit sur **invite de commandes**, puis sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="f0cc6-113">Ouvrez la console de gestion du module de plateforme sécurisée (TPM) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f0cc6-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="f0cc6-114">À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la version de votre spécification de TPM est d’au moins 1,2</span><span class="sxs-lookup"><span data-stu-id="f0cc6-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0cc6-115">Si vous recevez une boîte de dialogue indiquant qu’un module de plateforme de confiance compatible (TPM) est introuvable, vérifiez que l’ordinateur dispose d’un module TPM compatible et qu’il est activé dans le BIOS système.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="f0cc6-116">Fermer la console de gestion du TPM</span><span class="sxs-lookup"><span data-stu-id="f0cc6-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="f0cc6-117">À partir de l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f0cc6-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0cc6-118">Pour fournir une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez à la place/pin prompt.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="f0cc6-119">À partir de l’invite de commandes, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f0cc6-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="f0cc6-120">Dans la console de gestion de l’ordinateur, sélectionnez **gestion des appareils**.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="f0cc6-121">Développez **lecteurs de cartes à puce**.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="f0cc6-122">Vérifiez que le nouveau lecteur de carte à puce virtuelle a été créé avec succès.</span><span class="sxs-lookup"><span data-stu-id="f0cc6-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

