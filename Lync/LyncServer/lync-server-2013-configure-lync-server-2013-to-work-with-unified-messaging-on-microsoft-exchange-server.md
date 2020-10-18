---
title: 'Lync Server 2013 : configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server'
description: 'Lync Server 2013 : configurez Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05ef2902ffc03b14e04b378a2ef18e03c8c58372
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578040"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="81514-103">Configurer Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="81514-103">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="81514-104">_**Dernière modification de la rubrique :** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="81514-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="81514-105">Cette étape nécessite l’utilitaire d’intégration de la messagerie unifiée Exchange (OcsUmUtil.exe)).</span><span class="sxs-lookup"><span data-stu-id="81514-105">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="81514-106">Cet outil se trouve sur le serveur Lync Server 2013 dans le.. \\ Fichiers communs des fichiers programme \\ \\ dossier de \\ prise en charge de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81514-106">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="81514-107">Exécution de l’utilitaire d’intégration de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="81514-107">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="81514-108">L’utilitaire d’intégration de la messagerie unifiée Exchange doit être exécuté à partir d’un compte d’utilisateur présentant les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="81514-108">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="81514-109">l’appartenance aux groupes RTCUniversalServerAdmins et RtcUniversalUserAdmins (comprenant l’autorisation de lecture des paramètres de la messagerie unifiée Exchange Server) ;</span><span class="sxs-lookup"><span data-stu-id="81514-109">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="81514-110">Droits d’utilisateur au sein du domaine pour créer des objets contact dans le conteneur d’unités d’organisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="81514-110">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="81514-111">Lorsque vous exécutez l’utilitaire d’intégration de la messagerie unifiée Exchange, il exécute les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="81514-111">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="81514-112">Il créé des objets contact pour chaque numéro de standard automatique et numéro d’accès d’abonné dont les utilisateurs de Voix Entreprise se serviront.</span><span class="sxs-lookup"><span data-stu-id="81514-112">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="81514-113">Vérifie que le nom de chaque plan de numérotation voix entreprise correspond au contexte téléphonique du plan de numérotation de messagerie unifiée correspondant.</span><span class="sxs-lookup"><span data-stu-id="81514-113">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="81514-114">Cette correspondance est nécessaire uniquement si le plan de numérotation de messagerie unifiée est exécuté sur une version d’Exchange *antérieure* à Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="81514-114">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81514-115">Avant d’exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange, assurez-vous que vous avez réalisé les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="81514-115">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="81514-116">Créez un ou plusieurs plans de numérotation de messagerie unifiée Exchange, comme décrit dans la documentation du produit Exchange.</span><span class="sxs-lookup"><span data-stu-id="81514-116">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="81514-117">Pour Microsoft Exchange Server 2010, consultez &quot; la rubrique créer un plan de numérotation de messagerie unifiée &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> .</span><span class="sxs-lookup"><span data-stu-id="81514-117">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="81514-118">Pour Microsoft Exchange Server 2007 Service Pack 1 (SP1), consultez &quot; la rubrique How to Create a Unified Messaging SIP URI SIP dial plan &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> .</span><span class="sxs-lookup"><span data-stu-id="81514-118">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="81514-119">Créez un ou plusieurs plans de numérotation Lync Server correspondants, comme décrit dans <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="81514-119">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="81514-120">Si vous utilisez une version d’Exchange antérieure à Microsoft Exchange Server 2010 SP1, vous devez entrer le nom de domaine complet (FQDN) du plan de numérotation SIP de messagerie unifiée Exchange correspondant dans le champ <STRONG>nom simple</STRONG> du plan de numérotation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81514-120">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="81514-121">Si vous utilisez Microsoft Exchange Server 2010 SP1 ou le Service Pack le plus récent, cette correspondance de nom de plan de numérotation n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="81514-121">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="81514-122">Créez un standard automatique et assurez-vous que le numéro d’accès abonné et le numéro du standard automatique sont au format E.164.</span><span class="sxs-lookup"><span data-stu-id="81514-122">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="81514-123">Pour exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="81514-123">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="81514-124">Sur un serveur frontal, ouvrez une invite de commandes et tapez **cd% COMMONPROGRAMFILES% \\ Microsoft Lync Server 2013 \\ support**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="81514-124">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="81514-125">Tapez **OcsUmUtil.exe**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="81514-125">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="81514-126">Cliquez sur **Charger les données** pour rechercher toutes les forêts Exchange approuvées.</span><span class="sxs-lookup"><span data-stu-id="81514-126">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="81514-127">Dans la liste **Plans de numérotation SIP**, sélectionnez un plan de numérotation SIP de messagerie unifiée pour lequel vous souhaitez créer des objets contact, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81514-127">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="81514-p104">Dans la zone **Contact**, acceptez l’unité d’organisation par défaut, ou cliquez sur **Parcourir** pour démarrer le **Sélecteur d’unités d’organisation**. Dans la zone **Sélecteur d’unités d’organisation**, sélectionnez une unité d’organisation et cliquez sur **OK**. Vous pouvez aussi cliquer sur **Créer une unité d’organisation** pour créer une unité d’organisation sous la racine, ou toute autre unité d’organisation dans le domaine (par exemple, « OU=RTC Special Accounts,DC=fourthcoffee,DC=com »), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81514-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81514-130">Le nom unique de l’unité d’organisation que vous avez sélectionnée ou créée est désormais affiché dans la zone <STRONG>Unité d’organisation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="81514-130">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="81514-131">Dans la zone **Nom**, acceptez le nom de plan de numérotation par défaut, ou tapez un nouveau nom complet pour l’objet contact que vous créez.</span><span class="sxs-lookup"><span data-stu-id="81514-131">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81514-132">Par exemple, si vous créez un objet contact d’accès abonné, vous pouvez tout simplement le nommer Accès Abonné.</span><span class="sxs-lookup"><span data-stu-id="81514-132">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="81514-133">Dans la zone **Adresse SIP**, acceptez l’adresse SIP par défaut ou tapez une nouvelle adresse SIP.</span><span class="sxs-lookup"><span data-stu-id="81514-133">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81514-134">Si vous tapez une nouvelle adresse SIP, elle doit commencer par <STRONG>SIP:</STRONG> (c’est-à-dire, « SIP: » le signe : compris).</span><span class="sxs-lookup"><span data-stu-id="81514-134">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="81514-135">Dans la liste **serveur ou pool** , sélectionnez le serveur Standard Edition ou le pool frontal dans lequel l’objet contact doit être activé.</span><span class="sxs-lookup"><span data-stu-id="81514-135">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81514-136">Il est préférable de choisir le pool où les utilisateurs activés pour Voix Entreprise et la messagerie unifiée Exchange sont déployés.</span><span class="sxs-lookup"><span data-stu-id="81514-136">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="81514-137">Dans la liste **Numéro de téléphone**, sélectionnez **Entrez le numéro de téléphone** ou **Utilisez ce numéro pilote à partir d’Exchange UM**, puis entrez un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="81514-137">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="81514-138">Dans la liste **Type de contact**, sélectionnez le type de contact que vous souhaitez créer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81514-138">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="81514-139">Répétez les étapes 1 à 10 pour les objets contact supplémentaires que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="81514-139">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81514-p105">Vous devez créer au moins un contact pour chaque standard automatique. Si vous souhaitez un accès externe, vous devez également créer un contact d’accès abonné et spécifier des numéros SDA (Sélection directe à l’arrivée).</span><span class="sxs-lookup"><span data-stu-id="81514-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="81514-p106">Pour vérifier que les objets contact ont bien été créés, ouvrez Utilisateurs et ordinateurs Active Directory et sélectionnez l’unité d’organisation dans laquelle les objets ont été créés. Les objets contact apparaissent dans le volet d’informations.</span><span class="sxs-lookup"><span data-stu-id="81514-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="81514-144"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="81514-144"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

