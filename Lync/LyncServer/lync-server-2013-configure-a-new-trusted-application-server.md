---
title: 'Lync Server 2013: configurer un nouveau serveur d’applications de confiance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="632f8-102">Configurer un nouveau serveur d’applications de confiance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="632f8-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="632f8-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="632f8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="632f8-104">Une application fiable est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="632f8-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="632f8-105">Pour plus d’informations sur les applications UCMA, voir la documentation relative au kit de développement logiciel [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)unifié API 3,0 principal du SDK.</span><span class="sxs-lookup"><span data-stu-id="632f8-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="632f8-106">Pour plus d’informations sur la configuration de Microsoft Outlook Web Access (OWA) et de Lync Server 2013, voir «configurer Outlook Web App et intégration de Lync Server 2010» dans la documentation Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="632f8-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="632f8-107">Pour la publication, l’activation ou la désactivation d’une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="632f8-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="632f8-108">Il est également possible de déléguer les autorisations et les droits d’administrateur appropriés pour ajouter des rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="632f8-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="632f8-109">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="632f8-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="632f8-110">Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="632f8-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="632f8-111">Pour configurer un serveur d’applications de confiance</span><span class="sxs-lookup"><span data-stu-id="632f8-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="632f8-112">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="632f8-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="632f8-113">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="632f8-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="632f8-114">Sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="632f8-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="632f8-115">Dans la boîte de dialogue **enregistrer la topologie comme** , cliquez sur le fichier de générateur de topologie que vous voulez utiliser, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="632f8-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="632f8-116">Dans le volet gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance**, puis cliquez sur **nouveau pool d’applications approuvés**.</span><span class="sxs-lookup"><span data-stu-id="632f8-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="632f8-117">Entrez le **nom de domaine complet (FQDN** ) du pool d’applications de confiance, puis choisissez s’il s’agit d’un serveur unique ou d’un serveur, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="632f8-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="632f8-118">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="632f8-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="632f8-119">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="632f8-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="632f8-120">Sélectionnez le nœud supérieur **Lync Server 2013**, puis dans le menu **actions** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="632f8-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="632f8-121">Le **pool d’applications approuvé** doit avoir été créé avec succès et associé au pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="632f8-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

