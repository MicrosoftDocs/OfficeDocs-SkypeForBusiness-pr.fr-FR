---
title: 'Lync Server 2013: configuration de Windows 8 pour les cartes à puce virtuelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="0591a-102">Configuration de Windows 8 pour l’utilisation des cartes à puce virtuelles avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0591a-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0591a-103">_**Dernière modification de la rubrique:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="0591a-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="0591a-104">Le coût de mise en œuvre est l’un des facteurs à prendre en compte dans le cadre du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="0591a-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="0591a-105">Windows 8 fournit un certain nombre de nouvelles fonctionnalités de sécurité et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.</span><span class="sxs-lookup"><span data-stu-id="0591a-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="0591a-106">Pour les ordinateurs équipés d’une puce de module de plateforme sécurisée conforme à la spécification version 1.2, les organisations peuvent désormais tirer parti des avantages d’une ouverture de session par carte à puce sans investissement matériel supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0591a-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="0591a-107">Pour plus d’informations, reportez-vous à la rubrique [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)utilisation de cartes à puce virtuelles avec Windows 8.</span><span class="sxs-lookup"><span data-stu-id="0591a-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="0591a-108">Configuration de Windows 8 pour les cartes à puce virtuelles</span><span class="sxs-lookup"><span data-stu-id="0591a-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="0591a-109">Connectez-vous à l’ordinateur Windows 8 en utilisant les informations d’identification d’un utilisateur compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="0591a-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="0591a-110">Dans l’écran d’accueil de Windows 8, déplacez votre curseur dans le coin droit inférieur de l’écran.</span><span class="sxs-lookup"><span data-stu-id="0591a-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="0591a-111">Sélectionnez l’option **Rechercher**, puis recherchez **Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="0591a-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="0591a-112">Cliquez avec le bouton droit sur **Invite de commandes**, puis sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="0591a-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="0591a-113">Ouvrez la console de gestion du module de plateforme sécurisée en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0591a-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="0591a-114">À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la spécification du module de plateforme sécurisée correspond à la version 1.2 au minimum.</span><span class="sxs-lookup"><span data-stu-id="0591a-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0591a-115">Si un message indiquant qu’aucun module de plateforme sécurisée compatible n’a été trouvé, vérifiez que l’ordinateur dispose d’un module de plateforme sécurisée compatible et que celui-ci est activé dans le BIOS système.</span><span class="sxs-lookup"><span data-stu-id="0591a-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="0591a-116">Fermez la console de gestion du module de plateforme sécurisée.</span><span class="sxs-lookup"><span data-stu-id="0591a-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="0591a-117">Dans l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0591a-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0591a-118">Pour indiquer une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez plutôt l’invite /pin.</span><span class="sxs-lookup"><span data-stu-id="0591a-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="0591a-119">Dans l’invite de commandes, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0591a-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="0591a-120">Dans la console de gestion de l’ordinateur, sélectionnez **Gestion des périphériques**.</span><span class="sxs-lookup"><span data-stu-id="0591a-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="0591a-121">Développez **Lecteurs de cartes à puce**.</span><span class="sxs-lookup"><span data-stu-id="0591a-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="0591a-122">Vérifiez que le lecteur de cartes à puce virtuelles a bien été créé.</span><span class="sxs-lookup"><span data-stu-id="0591a-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

