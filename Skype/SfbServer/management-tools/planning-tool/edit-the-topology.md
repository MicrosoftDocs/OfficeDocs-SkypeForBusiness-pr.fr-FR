---
title: Modification de la topologie dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour ce faire, sur la page de la topologie globale, double-cliquez sur le site que vous souhaitez modifier.
ms.openlocfilehash: 7de778c9aed8594df4fc70f9a6635bd0c21c6db4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="65df7-104">Modification de la topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="65df7-104">Edit the topology in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="65df7-p102">Après avoir répondu aux questions initiales, vous pouvez modifier le nom de domaine complet et les adresses IP pour le site. Pour cela, sur la page **Topologie globale**, double-cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="65df7-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>
  
<span data-ttu-id="65df7-107">L’outil de planification affiche la topologie de site pour le site sélectionné.</span><span class="sxs-lookup"><span data-stu-id="65df7-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="65df7-108">Le bas de la page du site comporte quatre onglets :</span><span class="sxs-lookup"><span data-stu-id="65df7-108">At the bottom of the site page are four tabs:</span></span>
  
![Outil de planification - Topologie de site](../../media/Planning_Tool_Site_Topology.png)
  
- <span data-ttu-id="65df7-110">Topologie de site - la page actuellement affichée avec une présentation visuelle de la topologie, comme recommandé.</span><span class="sxs-lookup"><span data-stu-id="65df7-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>
    
- <span data-ttu-id="65df7-111">Diagramme de réseau de bord - la page de diagramme de réseau de bord est où le concepteur la plupart du travail de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="65df7-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="65df7-112">Le diagramme affiche la configuration réseau pour un Skype recommandée pour la topologie de Business Server 2015, avec des entrées modifiables pour IP adresses et noms de domaine complets pour serveurs, pool et à la fois matérielle et système de nom de domaine (DNS) les équilibreurs de charge.</span><span class="sxs-lookup"><span data-stu-id="65df7-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>
    
- <span data-ttu-id="65df7-113">Rapport Admin de bord - le rapport Admin de bord contient un total de quatre états :</span><span class="sxs-lookup"><span data-stu-id="65df7-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>
    
     ![Page Rapport d’administrateur Edge](../../media/Planning_Tool_Summary_Report.png)
  
  - <span data-ttu-id="65df7-115">Rapport de synthèse - un rapport général de paramètres pour la configuration de réseau de bord.</span><span class="sxs-lookup"><span data-stu-id="65df7-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="65df7-116">Si vous calez les valeurs de la page **Diagramme du réseau de périmètre** sur les valeurs des adresses TCP/IP et des noms de domaine complets qui seront utilisées dans la topologie du déploiement, ces adresses et noms seront représentés ici.</span><span class="sxs-lookup"><span data-stu-id="65df7-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="65df7-117">Sinon, les valeurs par défaut s’afficheront.</span><span class="sxs-lookup"><span data-stu-id="65df7-117">Otherwise, the default text will appear.</span></span>
    
  - <span data-ttu-id="65df7-118">Certificat de rapports - répertorie le nom du sujet et les noms d’objet alternatifs pour les certificats qui sont requis pour la topologie de l’état du certificat.</span><span class="sxs-lookup"><span data-stu-id="65df7-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
  - <span data-ttu-id="65df7-119">État du pare-feu - l’état du pare-feu répertorie les informations nécessaires à la configuration des pare-feu de périmètre dans l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="65df7-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="65df7-120">Il s’agit des adresses IP (valeurs par défaut ou valeurs modifiées), des rôles serveur, des ports et adresses IP source et de destination, des protocoles de transport, des protocoles d’application et de remarques pertinentes.</span><span class="sxs-lookup"><span data-stu-id="65df7-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
  - <span data-ttu-id="65df7-121">DNS - l’état DNS reprend des informations pertinentes pour les entrées DNS qui vous devez le créer.</span><span class="sxs-lookup"><span data-stu-id="65df7-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="65df7-122">Il s’agit du type d’enregistrement, du nom de domaine complet, de l’adresse IP et de commentaires nécessaires pour le bon fonctionnement du déploiement.</span><span class="sxs-lookup"><span data-stu-id="65df7-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>
    
- <span data-ttu-id="65df7-123">Résumé du site - le résumé du site présente une vue d’ensemble des sélections que vous avez apportées en répondant aux questions initiales ou en renseignant les valeurs de **Concevoir des Sites**.</span><span class="sxs-lookup"><span data-stu-id="65df7-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="65df7-124">Les informations de capacité sont également présentées.</span><span class="sxs-lookup"><span data-stu-id="65df7-124">Capacity information is also presented.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="65df7-125">Les informations sur la page Résumé du site sont propres à chaque conception. Par conséquent, certaines sections et informations détaillées ici peuvent ne pas s’afficher pour certaines conceptions.</span><span class="sxs-lookup"><span data-stu-id="65df7-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span> 
  
## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="65df7-126">Modifier le diagramme de configuration du réseau</span><span class="sxs-lookup"><span data-stu-id="65df7-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="65df7-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="65df7-127"></span></span>

<span data-ttu-id="65df7-128">La plupart du travail par un concepteur dans la Skype pour outil de planification de 2015 Business Server consiste à définir les entrées pour les adresses IP et les noms de domaine pleinement qualifié (FQDN) pour les écritures sur le réseau de tâches.</span><span class="sxs-lookup"><span data-stu-id="65df7-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="65df7-129">Les informations entrées sur cette page porte également ses fruits dans les rapports et les autres informations contenues dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="65df7-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span> 
  
![Outil de planification - Diagramme réseau](../../media/Planning_Tool_Network_Diagram.png)
  
<span data-ttu-id="65df7-131">L’outil de planification crée un diagramme de réseau avec un texte par défaut pour les adresses IP et noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="65df7-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span> 
  
<span data-ttu-id="65df7-132">Pour modifier le diagramme de réseau et les valeurs entrées :</span><span class="sxs-lookup"><span data-stu-id="65df7-132">To edit the network diagram and input values:</span></span>
  
1. <span data-ttu-id="65df7-p110">Commencez par choisir une section du réseau. Par exemple, double-cliquez sur le texte **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet (FQDN) réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="65df7-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>
    
2. <span data-ttu-id="65df7-135">Cliquez sur **OK** pour enregistrer les entrées.</span><span class="sxs-lookup"><span data-stu-id="65df7-135">Click **OK** to save the entries.</span></span>
    
3. <span data-ttu-id="65df7-136">Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.</span><span class="sxs-lookup"><span data-stu-id="65df7-136">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>
    
<span data-ttu-id="65df7-p111">Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="65df7-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>
  
1. <span data-ttu-id="65df7-p112">Double-cliquez sur les serveurs frontaux du pool. Quand la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.</span><span class="sxs-lookup"><span data-stu-id="65df7-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span> 
    
2. <span data-ttu-id="65df7-141">Dans l’exemple, la valeur de démarrage pour le premier serveur est fe0101.contoso.com avec l’adresse IP 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="65df7-141">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>
    
3. <span data-ttu-id="65df7-142">Tapez fe0.contoso.com dans le **FQDN de serveur frontal fin**, 192.168.21.131 dans **l’adresse IP de serveur avant fin**et puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65df7-142">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="65df7-143">La fonction d’incrémentation automatique met à jour tous les serveurs du pool entre fe01 et fe06, et toutes les adresses IP entre 192.168.21.131 et 136.</span><span class="sxs-lookup"><span data-stu-id="65df7-143">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>
    
<span data-ttu-id="65df7-144">Une fois toutes les modifications terminées, enregistrez la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="65df7-144">After you have completed all edits, save the topology by completing the following steps:</span></span> 
  
<span data-ttu-id="65df7-145">Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis cliquez sur **Enregistrer la topologie** ou **Enregistrer la topologie sous**.</span><span class="sxs-lookup"><span data-stu-id="65df7-145">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="65df7-146">Si une boîte de dialogue **Enregistrer l’outil de planification sous** s’affiche, tapez un nom pour le fichier dans **Nom de fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="65df7-146">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="65df7-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65df7-147">See also</span></span>
<span data-ttu-id="65df7-148"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="65df7-148"></span></span>

#### 

[<span data-ttu-id="65df7-149">Modification de la conception</span><span class="sxs-lookup"><span data-stu-id="65df7-149">Editing the Design</span></span>](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

