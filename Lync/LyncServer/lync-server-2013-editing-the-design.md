---
title: 'Lync Server 2013 : modification de la conception'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f6fa93dbb7ab1ad33b8972b8f09a025dec58c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="45c26-102">Modification de la conception dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45c26-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45c26-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="45c26-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="45c26-104">Une fois que vous avez terminé les questions initiales de l’entretien, vous pouvez modifier le nom de domaine complet (FQDN) et les adresses IP pour le site.</span><span class="sxs-lookup"><span data-stu-id="45c26-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="45c26-105">Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="45c26-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="45c26-106">L’outil de planification affiche la topologie de site pour le site sélectionné.</span><span class="sxs-lookup"><span data-stu-id="45c26-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="45c26-107">Le bas de la page du site comporte quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="45c26-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="45c26-108">![Outil de planification topologie de site](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Outil de planification topologie de site")</span><span class="sxs-lookup"><span data-stu-id="45c26-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="45c26-109">Topologie du site – La page affichée avec une représentation visuelle de la topologie recommandée.</span><span class="sxs-lookup"><span data-stu-id="45c26-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="45c26-110">Diagramme de réseau Edge : la page réseau de tâches Edge est l’endroit où le concepteur effectue la plus grande partie du travail dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="45c26-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="45c26-111">Le diagramme affiche la configuration réseau d’une topologie Lync Server 2013 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets (FQDN) des serveurs, des pools et des équilibreurs de charge DNS (Domain Name System) et physiques.</span><span class="sxs-lookup"><span data-stu-id="45c26-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="45c26-112">Rapport de l’administrateur du périmètre – Ce rapport contient quatre rapports :</span><span class="sxs-lookup"><span data-stu-id="45c26-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="45c26-113">![Page rapport d’administration Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Page rapport d’administration Edge")</span><span class="sxs-lookup"><span data-stu-id="45c26-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="45c26-114">Rapport récapitulatif – Rapport général des paramètres de la configuration du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="45c26-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="45c26-115">Si vous modifiez les valeurs de la page **réseau de tâches Edge** sur le port TCP/IP de topologie et que les valeurs de nom de domaine complet de sont utilisées dans le déploiement réel, ces adresses et noms seront représentés ici.</span><span class="sxs-lookup"><span data-stu-id="45c26-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="45c26-116">Dans le cas contraire, le texte par défaut s’affiche.</span><span class="sxs-lookup"><span data-stu-id="45c26-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="45c26-117">Rapport sur les certificats – Ce rapport répertorie les noms de sujet et les noms de sujet alternatifs requis pour la topologie.</span><span class="sxs-lookup"><span data-stu-id="45c26-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="45c26-118">Rapport sur les pare-feu – Ce rapport répertorie les informations nécessaires pour configurer les pare-feu du périmètre dans l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="45c26-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="45c26-119">Cela inclut les adresses IP (valeurs par défaut ou valeurs modifiées), le rôle serveur, l’adresse IP et le port source, l’adresse IP et le port de destination, le protocole de transport, le protocole d’application et les remarques pertinentes.</span><span class="sxs-lookup"><span data-stu-id="45c26-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="45c26-120">Rapport DNS : le rapport DNS répertorie les informations pertinentes pour les entrées DNS que vous devez créer.</span><span class="sxs-lookup"><span data-stu-id="45c26-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="45c26-121">Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.</span><span class="sxs-lookup"><span data-stu-id="45c26-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="45c26-122">Résumé du site : le résumé du site présente une vue d’ensemble des sélections effectuées en répondant aux questions initiales de l’entretien ou en remplissant les valeurs dans les **sites de conception**.</span><span class="sxs-lookup"><span data-stu-id="45c26-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="45c26-123">Des informations sur la capacité sont également présentées.</span><span class="sxs-lookup"><span data-stu-id="45c26-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45c26-124">Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas apparaître pour certaines conceptions.</span><span class="sxs-lookup"><span data-stu-id="45c26-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="45c26-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45c26-125">See Also</span></span>


[<span data-ttu-id="45c26-126">Modification du diagramme de configuration réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45c26-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

