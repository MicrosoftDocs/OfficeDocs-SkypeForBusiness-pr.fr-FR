---
title: 'Lync Server 2013 : Modification de la conception'
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
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="1c530-102">Modification de la conception dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c530-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c530-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1c530-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1c530-p101">Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="1c530-p101">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="1c530-106">L’outil de planification affiche la topologie de site pour le site sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1c530-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="1c530-107">Le bas de la page du site comporte quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="1c530-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="1c530-108">![Topologie de site outil de planification](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologie de site outil de planification")</span><span class="sxs-lookup"><span data-stu-id="1c530-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="1c530-109">Topologie du site - La page affichée avec une représentation visuelle de la topologie recommandée.</span><span class="sxs-lookup"><span data-stu-id="1c530-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="1c530-110">Diagramme de réseau Edge : la page de diagramme de réseau Edge est l’endroit où le concepteur exécute la majeure partie du travail dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="1c530-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="1c530-111">Le diagramme affiche la configuration réseau pour une topologie Lync Server 2013 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, le pool, et les équilibreurs de charge du système de noms de domaine et de domaine (DNS).</span><span class="sxs-lookup"><span data-stu-id="1c530-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="1c530-112">Rapport de l’administrateur du périmètre - Ce rapport contient quatre rapports :</span><span class="sxs-lookup"><span data-stu-id="1c530-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="1c530-113">![Page rapport d’administration Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Page rapport d’administration Edge")</span><span class="sxs-lookup"><span data-stu-id="1c530-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="1c530-p104">Rapport récapitulatif - Rapport général des paramètres de la configuration du réseau de périmètre. Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici. Sinon, les valeurs par défaut s’afficheront.</span><span class="sxs-lookup"><span data-stu-id="1c530-p104">Summary Report – A general report of settings for the Edge network configuration. If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here. Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="1c530-117">Rapport sur les certificats - Ce rapport répertorie les noms de sujet et les noms de sujet alternatifs requis pour la topologie.</span><span class="sxs-lookup"><span data-stu-id="1c530-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="1c530-p105">Rapport sur les pare-feu - Ce rapport répertorie les informations nécessaires pour configurer les pare-feu du périmètre dans l’infrastructure. Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.</span><span class="sxs-lookup"><span data-stu-id="1c530-p105">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure. This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="1c530-p106">Rapport DNS - Ce rapport répertorie les informations pertinentes pour les entrées DNS que vous devez créer. Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.</span><span class="sxs-lookup"><span data-stu-id="1c530-p106">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create. The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="1c530-p107">Résumé du site - Le résumé du site présente une vue d’ensemble des sélections que vous avez effectuées en répondant aux questions initiales ou en indiquant les valeurs dans **Concevoir des sites**. Les informations de capacité sont également présentées.</span><span class="sxs-lookup"><span data-stu-id="1c530-p107">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**. Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c530-124">Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions.</span><span class="sxs-lookup"><span data-stu-id="1c530-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c530-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c530-125">See Also</span></span>


[<span data-ttu-id="1c530-126">Modification du diagramme de configuration réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c530-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

