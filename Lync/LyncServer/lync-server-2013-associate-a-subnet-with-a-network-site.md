---
title: 'Lync Server 2013 : associer un sous-réseau à un site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d41e5959eaf596faaed25a9759534a9156f0d9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="639d1-102">Associer un sous-réseau à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="639d1-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="639d1-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="639d1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="639d1-104">Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique, car les informations de sous-réseau servent à définir le site réseau sur lequel figure un système d’extrémité lorsqu’une nouvelle session est initiée.</span><span class="sxs-lookup"><span data-stu-id="639d1-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="639d1-105">Lorsque l’emplacement de chaque partie d’une session est connu, les fonctionnalités avancées de voix entreprise peuvent appliquer ces informations pour déterminer comment gérer la configuration de l’appel ou le routage.</span><span class="sxs-lookup"><span data-stu-id="639d1-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="639d1-106">Toutes les adresses IP publiques configurées des serveurs Edge audio/vidéo de votre déploiement doivent être ajoutées à vos paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="639d1-107">Ces adresses IP sont ajoutées sous forme de sous-réseaux avec un masque de 32.</span><span class="sxs-lookup"><span data-stu-id="639d1-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="639d1-108">Le site réseau associé doit correspondre au site réseau configuré approprié.</span><span class="sxs-lookup"><span data-stu-id="639d1-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="639d1-109">Par exemple, l’adresse IP publique correspondant au serveur Edge A/V du site central Chicago serait NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="639d1-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="639d1-110">Pour plus d’informations sur les adresses IP publiques, voir <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determine External A/V Firewall and Port Requirements for Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="639d1-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="639d1-p103">Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de huit heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="639d1-p103">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8-hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="639d1-114"><STRONG>Source :</STRONG> Service de stratégie de bande passante CS (Core)</span><span class="sxs-lookup"><span data-stu-id="639d1-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="639d1-115"><STRONG>Numéro d’événement :</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="639d1-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="639d1-116"><STRONG>Niveau :</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="639d1-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="639d1-117"><STRONG>Description :</STRONG> Les sous-réseaux pour les adresses IP suivantes &lt;: la liste des&gt; adresses IP n’est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="639d1-118"><STRONG>Cause :</STRONG> Les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="639d1-119"><STRONG>Résolution :</STRONG> Ajoutez des sous-réseaux correspondant à la liste des adresses IP dans les paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="639d1-p104">Par exemple, si la liste d’adresses IP qui apparaît dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :</span><span class="sxs-lookup"><span data-stu-id="639d1-p104">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="639d1-122">Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="639d1-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="639d1-123">Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="639d1-124">Pour plus d’informations sur l’utilisation des sous-réseaux, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="639d1-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="639d1-125">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="639d1-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="639d1-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="639d1-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="639d1-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="639d1-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="639d1-128">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="639d1-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="639d1-p105">Si vous utilisez un grand nombre de sous-réseaux, nous vous recommandons d’utiliser un fichier de valeurs séparées par des virgules (CSV) pour associer les sous-réseaux à des sites. Le fichier CSV doit comporter les quatre colonnes suivantes : <STRONG>adresse IP</STRONG>, <STRONG>masque</STRONG>, <STRONG>description</STRONG>, <STRONG>ID de site réseau</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="639d1-p105">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites. The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="639d1-131">Pour associer un sous-réseau à un site réseau à l’aide de Management Shell</span><span class="sxs-lookup"><span data-stu-id="639d1-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="639d1-132">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="639d1-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="639d1-133">Exécutez l’applet de commande **New-CsNetworkSubnet** pour associer un sous-réseau à un site réseau :</span><span class="sxs-lookup"><span data-stu-id="639d1-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="639d1-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="639d1-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="639d1-135">Dans cet exemple, vous avez créé une association entre le sous-réseau 172.11.12.13 et le site réseau « Chicago ».</span><span class="sxs-lookup"><span data-stu-id="639d1-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="639d1-136">Répétez l’étape 2 pour tous les sous-réseaux de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="639d1-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="639d1-137">Pour associer des sous-réseaux à des sites réseau en important un fichier CSV</span><span class="sxs-lookup"><span data-stu-id="639d1-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="639d1-p106">Créez un fichier CSV incluant tous les sous-réseaux que vous souhaitez ajouter. Par exemple, créez un fichier **subnet.csv** avec le contenu suivant :</span><span class="sxs-lookup"><span data-stu-id="639d1-p106">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="639d1-140">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="639d1-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="639d1-141">Exécutez l’applet de commande suivante pour importer le fichier **subnet. csv**, puis enregistrez son contenu dans le magasin de gestion Lync Server :</span><span class="sxs-lookup"><span data-stu-id="639d1-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="639d1-142">Pour associer un sous-réseau à un site réseau à l’aide du Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="639d1-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="639d1-143">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="639d1-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="639d1-144">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="639d1-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="639d1-145">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="639d1-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="639d1-146">Cliquez sur le bouton de navigation **Sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="639d1-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="639d1-147">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="639d1-147">Click **New**.</span></span>

5.  <span data-ttu-id="639d1-148">Dans la page **Nouveau sous-réseau**, cliquez sur **ID de sous-réseau**, puis entrez la première adresse de la plage d’adresses IP définie par le sous-réseau que vous souhaitez associer à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="639d1-149">Cliquez sur **Masque**, puis entrez le masque de bits à appliquer au sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="639d1-150">Cliquez sur **ID de site réseau**, puis sélectionnez l’ID du site auquel vous ajoutez ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="639d1-151">Si vous n’avez pas encore créé de sites réseau, cette liste est vide.</span><span class="sxs-lookup"><span data-stu-id="639d1-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="639d1-152">Pour plus d’informations sur la procédure, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or Modify a Network site in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="639d1-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="639d1-153">Vous pouvez également récupérer des ID de site pour votre déploiement en exécutant l’applet de commande <STRONG>Get-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="639d1-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="639d1-154">Pour plus d’informations, voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="639d1-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="639d1-155">Éventuellement, cliquez sur **Description**, puis entrez des informations supplémentaires pour décrire ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="639d1-156">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="639d1-156">Click **Commit**.</span></span>

<span data-ttu-id="639d1-157">Répétez ces étapes pour ajouter d’autres sous-réseaux à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="639d1-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

