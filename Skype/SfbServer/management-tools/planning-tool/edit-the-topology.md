---
title: Modification de la topologie dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page Topologie globale, double-cliquez sur le site que vous souhaitez modifier.
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816443"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="9abb9-104">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9abb9-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="9abb9-p102">Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="9abb9-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="9abb9-107">L’outil de planification affiche la topologie de site pour le site sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9abb9-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="9abb9-108">Le bas de la page du site comporte quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="9abb9-108">At the bottom of the site page are four tabs:</span></span>

![Topologie de site outil de planification](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="9abb9-110">Topologie de site : page actuellement affichée avec une vue d’ensemble visuelle de la topologie recommandée.</span><span class="sxs-lookup"><span data-stu-id="9abb9-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="9abb9-111">Diagramme de réseau Edge : la page réseau de tâches Edge est l’endroit où le concepteur effectue la majeure partie du travail dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="9abb9-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="9abb9-112">Le diagramme affiche la configuration du réseau pour une topologie 2015 de Skype entreprise Server, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, le pool, et les équilibreurs de charge de matériel et de système de noms de domaine (DNS).</span><span class="sxs-lookup"><span data-stu-id="9abb9-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="9abb9-113">Rapport d’administration Edge : le rapport d’administration Edge comporte au total quatre rapports :</span><span class="sxs-lookup"><span data-stu-id="9abb9-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Page rapport d’administration Edge](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="9abb9-115">Rapport de synthèse-un rapport général sur les paramètres de configuration du réseau Edge.</span><span class="sxs-lookup"><span data-stu-id="9abb9-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="9abb9-116">Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici.</span><span class="sxs-lookup"><span data-stu-id="9abb9-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="9abb9-117">Sinon, les valeurs par défaut s’afficheront.</span><span class="sxs-lookup"><span data-stu-id="9abb9-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="9abb9-118">Rapport de certification-le rapport de certificat indique le nom de l’objet et les noms de remplacement de l’objet pour les certificats requis pour la topologie.</span><span class="sxs-lookup"><span data-stu-id="9abb9-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="9abb9-119">Rapport de pare-feu-le rapport de pare-feu recense les informations nécessaires à la configuration des pare-feux de périmètre dans l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="9abb9-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="9abb9-120">Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.</span><span class="sxs-lookup"><span data-stu-id="9abb9-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="9abb9-121">Rapport DNS-le rapport DNS recense les informations pertinentes pour les entrées DNS que vous devez créer.</span><span class="sxs-lookup"><span data-stu-id="9abb9-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="9abb9-122">Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.</span><span class="sxs-lookup"><span data-stu-id="9abb9-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="9abb9-123">Résumé du site-le résumé du site offre une vue d’ensemble des sélections que vous avez apportées en répondant aux questions d’une interview initiale ou en remplissant les valeurs des **sites de conception**.</span><span class="sxs-lookup"><span data-stu-id="9abb9-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="9abb9-124">Les informations de capacité sont également présentées.</span><span class="sxs-lookup"><span data-stu-id="9abb9-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9abb9-125">Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions.</span><span class="sxs-lookup"><span data-stu-id="9abb9-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="9abb9-126">Modifier le diagramme de configuration du réseau</span><span class="sxs-lookup"><span data-stu-id="9abb9-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="9abb9-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="9abb9-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="9abb9-128">La plupart des tâches que le concepteur effectue dans l’outil de planification de Skype entreprise Server 2015 consiste à définir les entrées pour les adresses IP et les noms de domaine complets (FQDN) pour les entrées sur le réseau de tâches.</span><span class="sxs-lookup"><span data-stu-id="9abb9-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="9abb9-129">Les informations entrées dans cette page sont incluses dans les rapports et autres informations contenus dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="9abb9-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Diagramme du réseau d’outils de planification](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="9abb9-131">L’outil de planification crée un diagramme de réseau avec le texte par défaut pour les adresses IP et les noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="9abb9-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="9abb9-132">Pour modifier le diagramme de réseau et les valeurs entrées :</span><span class="sxs-lookup"><span data-stu-id="9abb9-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="9abb9-p110">Commencez par choisir une section du réseau. Par exemple, double-cliquez sur le texte **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet (FQDN) réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="9abb9-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="9abb9-136">Cliquez sur **OK** pour enregistrer les entrées.</span><span class="sxs-lookup"><span data-stu-id="9abb9-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="9abb9-137">Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.</span><span class="sxs-lookup"><span data-stu-id="9abb9-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="9abb9-p111">Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9abb9-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="9abb9-p112">Double-cliquez sur les serveurs frontaux du pool. Quand la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.</span><span class="sxs-lookup"><span data-stu-id="9abb9-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="9abb9-142">Dans l’exemple, la valeur de démarrage pour le premier serveur est fe0101.contoso.com avec l’adresse IP 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="9abb9-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="9abb9-143">Tapez fe0.contoso.com dans le **nom de domaine complet du serveur frontal**, tapez 192.168.21.131 dans l’**Adresse IP du serveur frontal**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9abb9-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="9abb9-144">La fonction d’incrémentation automatique met à jour tous les serveurs du pool entre fe01 et fe06, et toutes les adresses IP entre 192.168.21.131 et 136.</span><span class="sxs-lookup"><span data-stu-id="9abb9-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="9abb9-145">Une fois toutes les modifications terminées, enregistrez la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="9abb9-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="9abb9-146">Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis sur **enregistrer la topologie** ou **enregistrer la topologie sous**.</span><span class="sxs-lookup"><span data-stu-id="9abb9-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="9abb9-147">Si une boîte de dialogue **Enregistrer l’outil de planification sous** s’affiche, tapez un nom pour le fichier dans **Nom de fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9abb9-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9abb9-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9abb9-148">See also</span></span>
<span data-ttu-id="9abb9-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="9abb9-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="9abb9-150">Editing the Design</span><span class="sxs-lookup"><span data-stu-id="9abb9-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
