---
title: Modifier la topologie dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet (FQDN) et les adresses IP du site. Pour cela, sur la page Topologie globale, double-cliquez sur le site que vous souhaitez modifier.
ms.openlocfilehash: ba18070b21494028d31b4167ab92a622794c5e51
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834884"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="07477-104">Modifier la topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="07477-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="07477-105">Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet (FQDN) et les adresses IP du site.</span><span class="sxs-lookup"><span data-stu-id="07477-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="07477-106">Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="07477-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="07477-107">L’outil de planification affiche la topologie de site pour le site sélectionné.</span><span class="sxs-lookup"><span data-stu-id="07477-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="07477-108">Le bas de la page du site comporte quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="07477-108">At the bottom of the site page are four tabs:</span></span>

![Topologie du site de l’outil de planification](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="07477-110">Topologie de site : page actuellement affichée avec une vue d’ensemble visuelle de la topologie, comme recommandé.</span><span class="sxs-lookup"><span data-stu-id="07477-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="07477-111">Réseau de réseau de périphérie - La page Réseau de réseau de périphérie est l’endroit où le concepteur fait la majeure partie du travail dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="07477-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="07477-112">Le diagramme affiche la configuration réseau pour une topologie Skype Entreprise Server 2015 recommandée, avec des entrées modifiables pour les adresses IP et les noms de domaine complets pour les serveurs, le pool et les équilibreurs de charge matériels et DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="07477-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="07477-113">Rapport d’administration Edge - Le rapport d’administration Edge contient un total de quatre rapports :</span><span class="sxs-lookup"><span data-stu-id="07477-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Page Rapport de l’administrateur Edge](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="07477-115">Rapport de synthèse : rapport général sur les paramètres de configuration du réseau Edge.</span><span class="sxs-lookup"><span data-stu-id="07477-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="07477-116">Si vous modifiez les valeurs de la **page** Réseau de réseau de périphérie en valeurs de topologie TCP/IP et FQDN qui seront utilisées dans le déploiement réel, ces adresses et noms seront représentés ici.</span><span class="sxs-lookup"><span data-stu-id="07477-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="07477-117">Sinon, le texte par défaut s’affiche.</span><span class="sxs-lookup"><span data-stu-id="07477-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="07477-118">Rapport de certificat : le rapport de certificats indique le nom du sujet et les autres noms du sujet pour les certificats requis pour la topologie.</span><span class="sxs-lookup"><span data-stu-id="07477-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="07477-119">Rapport de pare-feu : le rapport de pare-feu répertorie les informations nécessaires pour configurer les pare-feu de périmètre dans l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="07477-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="07477-120">Cela inclut les adresses IP (valeurs par défaut ou modifiées), le rôle serveur, l’adresse IP source et le port, l’adresse IP et le port de destination, le protocole de transport, le protocole d’application et les notes pertinentes.</span><span class="sxs-lookup"><span data-stu-id="07477-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="07477-121">Rapport DNS : le rapport DNS répertorie les informations pertinentes pour les entrées DNS que vous devez créer.</span><span class="sxs-lookup"><span data-stu-id="07477-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="07477-122">Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.</span><span class="sxs-lookup"><span data-stu-id="07477-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="07477-123">Résumé du site : le résumé du site présente une vue d’ensemble des sélections que vous avez réalisées en répondant aux questions initiales ou en remplissant les valeurs des sites de **conception.**</span><span class="sxs-lookup"><span data-stu-id="07477-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="07477-124">Des informations sur la capacité sont également présentées.</span><span class="sxs-lookup"><span data-stu-id="07477-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07477-125">Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas apparaître pour certaines conceptions.</span><span class="sxs-lookup"><span data-stu-id="07477-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="07477-126">Modifier le diagramme de configuration réseau</span><span class="sxs-lookup"><span data-stu-id="07477-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="07477-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="07477-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="07477-128">La majeure partie du travail qu’un concepteur fait dans l’outil de planification de Skype Entreprise Server 2015 consiste à définir les entrées pour les adresses IP et les noms de domaine complets (FQDN) pour les entrées sur le diagramme réseau.</span><span class="sxs-lookup"><span data-stu-id="07477-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="07477-129">Les informations entrées sur cette page sont contenues dans les rapports et les autres informations contenues dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="07477-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Diagramme réseau de l’outil de planification](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="07477-131">L’outil de planification crée un diagramme réseau avec du texte par défaut pour les adresses IP et les noms de groupe.</span><span class="sxs-lookup"><span data-stu-id="07477-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="07477-132">Pour modifier le diagramme de réseau et les valeurs entrées :</span><span class="sxs-lookup"><span data-stu-id="07477-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="07477-133">Choisissez la section du réseau sur laquelle vous souhaitez commencer à travailler.</span><span class="sxs-lookup"><span data-stu-id="07477-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="07477-134">Par exemple, double-cliquez sur le **texte, access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="07477-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="07477-135">Dans la boîte de dialogue qui s’ouvre, tapez le nom deqdn réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant le 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="07477-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="07477-136">Cliquez sur **OK** pour enregistrer les entrées.</span><span class="sxs-lookup"><span data-stu-id="07477-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="07477-137">Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.</span><span class="sxs-lookup"><span data-stu-id="07477-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="07477-p111">Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07477-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="07477-140">Double-cliquez sur les serveurs frontaux du pool.</span><span class="sxs-lookup"><span data-stu-id="07477-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="07477-141">Lorsque la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.</span><span class="sxs-lookup"><span data-stu-id="07477-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="07477-142">Par exemple, la valeur de départ du premier serveur est fe0101.contoso.com et l’adresse IP 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="07477-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="07477-143">Tapez fe0.contoso.com **FQDN** du serveur frontal, tapez 192.168.21.131 dans l’adresse IP du serveur **frontal,** puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="07477-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="07477-144">La fonctionnalité d’incrémentation automatique met à jour tous les serveurs du pool vers fe01 à fe06, et toutes les adresses IP de 192.168.21.131 à 136.</span><span class="sxs-lookup"><span data-stu-id="07477-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="07477-145">Une fois toutes les modifications terminées, enregistrez la topologie en effectuant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="07477-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="07477-146">Pour enregistrer la conception de l’outil de planification, cliquez sur **Fichier,** puis sur Enregistrer la **topologie** ou **Enregistrer la topologie sous**.</span><span class="sxs-lookup"><span data-stu-id="07477-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="07477-147">Si une boîte de dialogue **Enregistrer l’outil de planification sous le nom** s’affiche, tapez un nom pour le fichier dans **Nom du fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="07477-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="07477-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07477-148">See also</span></span>
<span data-ttu-id="07477-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="07477-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="07477-150">Modification de la conception</span><span class="sxs-lookup"><span data-stu-id="07477-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
