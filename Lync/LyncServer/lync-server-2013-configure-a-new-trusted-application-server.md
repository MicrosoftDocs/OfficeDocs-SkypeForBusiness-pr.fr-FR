---
title: 'Lync Server 2013 : configuration d’un nouveau serveur d’applications approuvées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4d01e817e1a874af8c6beccdee332f85cc79ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="5d4c2-102">Configurer un nouveau serveur d’applications approuvées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d4c2-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d4c2-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5d4c2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5d4c2-104">Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5d4c2-105">Pour plus d’informations sur les applications UCMA, voir «documentation du [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320)Kit de développement logiciel (SDK) Unified Communications Managed API 3,0.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="5d4c2-106">Pour plus d’informations sur la configuration de Microsoft Outlook Web Access (OWA) et de Lync Server 2013, voir « Configurer l’intégration d’Outlook Web App et de Lync Server 2010 » dans la documentation de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="5d4c2-107">Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="5d4c2-108">Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour l’ajout de rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="5d4c2-109">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="5d4c2-110">Pour procéder à d’autres modifications de la configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="5d4c2-111">Pour configurer un serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="5d4c2-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="5d4c2-112">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="5d4c2-113">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="5d4c2-114">Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5d4c2-115">Dans la boîte de dialogue **enregistrer la topologie sous** , cliquez sur le fichier du générateur de topologies que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="5d4c2-116">Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications approuvées**, puis cliquez sur **nouveau pool d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="5d4c2-117">Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="5d4c2-118">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="5d4c2-119">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="5d4c2-120">Sélectionnez le nœud supérieur **Lync Server 2013**, puis, dans le menu **actions** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="5d4c2-121">Le **pool d’applications approuvées** doit avoir été créé avec succès et associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="5d4c2-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

