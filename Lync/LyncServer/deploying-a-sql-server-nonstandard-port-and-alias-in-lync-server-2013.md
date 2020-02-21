---
title: Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51d102c6a810730d6c748dafc6a4fcdc3dd6821e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="3213d-102">Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3213d-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3213d-103">_**Dernière modification de la rubrique :** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="3213d-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="3213d-104">Microsoft Lync Server 2013 prend en charge l’utilisation d’un alias et d’un port non standard dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="3213d-105">L’utilisation d’un port SQL Server non standard et d’un alias augmente la sécurité et crée un environnement plus flexible pour le déploiement Lync.</span><span class="sxs-lookup"><span data-stu-id="3213d-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="3213d-106">Ces étapes ne constituent qu’une seule étape de sécurisation de votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="3213d-107">Des étapes supplémentaires doivent être prises pour réduire la surface d’attaque d’une implémentation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="3213d-108">L’article suivant décrit les étapes à suivre pour configurer un alias et un port non standard SQL Server dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="3213d-109">Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3213d-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="3213d-110">Le générateur de topologies Lync Server 2013 prend en charge l’utilisation d’un alias SQL Server comme nom de domaine complet (FQDN) au lieu du nom de domaine complet SQL Server réel lors de la configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="3213d-111">Cela permet de masquer le nom de domaine complet SQL Server réel à un utilisateur malveillant.</span><span class="sxs-lookup"><span data-stu-id="3213d-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="3213d-112">En outre, l’utilisation d’un port non standard masque le port réel de tout agresseur tentant d’attaquer la base de données sur le port 1433 standard, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="3213d-113">![Un pirate ne connaît pas le numéro de port à attaquer.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirate ne connaît pas le numéro de port à attaquer.")</span><span class="sxs-lookup"><span data-stu-id="3213d-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="3213d-114">Pour réussir à déterminer le port que Lync Server 2013 utilise pour communiquer avec SQL Server, l’agresseur doit analyser tous les ports pour obtenir les informations sur les ports.</span><span class="sxs-lookup"><span data-stu-id="3213d-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="3213d-115">Une analyse des ports par un agresseur augmente les risques que la sécurité peut détecter et arrêter l’instruction.</span><span class="sxs-lookup"><span data-stu-id="3213d-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="3213d-116">En plus d’ajouter une sécurité accrue avec un port non standard, vous pouvez également utiliser un alias SQL Server pour assurer la flexibilité du déploiement.</span><span class="sxs-lookup"><span data-stu-id="3213d-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="3213d-117">Cela est utile afin de réduire les modifications de configuration dans les situations où un changement de nom SQL Server est requis.</span><span class="sxs-lookup"><span data-stu-id="3213d-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3213d-118">SQL Server fournit deux méthodes de tolérance de panne (clustering et mise en miroir de basculement).</span><span class="sxs-lookup"><span data-stu-id="3213d-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="3213d-119">Les deux méthodes de tolérance de panne SQL Server sont prises en charge à l’aide d’un alias et d’un port non standard SQL Server avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="3213d-120">Si le serveur principal SQL Server utilisé par le pool est dans une configuration mise en miroir, le service SQL Browser sur les serveurs principaux SQL Server doit être en cours d’exécution pour que les serveurs frontaux se connectent à la base de données mise en miroir lorsque les bases de données sont basculées vers le SQL en miroir. Serveurs.</span><span class="sxs-lookup"><span data-stu-id="3213d-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="3213d-121">Lors de la configuration de la connectivité de base de données SQL Server dans le générateur de topologie, ou lors de l’utilisation de la cmdlet install-applet csdatabase, il n’est pas possible de définir explicitement un numéro de port non standard SQL Server et de l’associer à une instance SQL.</span><span class="sxs-lookup"><span data-stu-id="3213d-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="3213d-122">Pour définir un port non standard, vous devez utiliser SQL Server et les utilitaires Windows Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="3213d-123">Pour configurer un alias et un port non standard SQL Server à utiliser avec Lync Server 2013, vous devez effectuer les trois étapes principales.</span><span class="sxs-lookup"><span data-stu-id="3213d-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="3213d-124">Voici la procédure à suivre :</span><span class="sxs-lookup"><span data-stu-id="3213d-124">These steps are:</span></span>

  - <span data-ttu-id="3213d-125">Vérifiez que les mises à jour les plus récentes sont appliquées à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="3213d-126">Configurez le port et l’alias non standard de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="3213d-127">Configurez Lync Server 2013 avec l’alias SQL Server à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3213d-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="3213d-128">Publiez la topologie et vérifiez la base de données.</span><span class="sxs-lookup"><span data-stu-id="3213d-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="3213d-129">Vérifiez que les mises à jour les plus récentes sont appliquées à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3213d-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="3213d-130">Il est important de tenir à jour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="3213d-131">Pour vérifier les mises à jour les plus récentes et obtenir des informations sur leur application, voir [mises à jour pour Lync Server 2013](https://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="3213d-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="3213d-132">Configurer le port et l’alias non standard de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3213d-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="3213d-133">Le port et l’alias SQL Server non standard doivent être configurés sur l’instance de base de données pour pouvoir être référencés à partir du générateur de topologies Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="3213d-134">Pour configurer un alias et un port non standard SQL Server, vous devez effectuer les trois étapes principales.</span><span class="sxs-lookup"><span data-stu-id="3213d-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="3213d-135">Ces étapes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3213d-135">These steps are as follows:</span></span>

  - <span data-ttu-id="3213d-136">Modifier les valeurs par défaut du protocole TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="3213d-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="3213d-137">Créez et configurez un alias SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="3213d-138">Créez un enregistrement de ressource de nom canonique DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="3213d-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="3213d-139">**Modifier les valeurs par défaut du protocole TCP/IP**</span><span class="sxs-lookup"><span data-stu-id="3213d-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="3213d-140">Sélectionnez **Démarrer**, puis **Gestionnaire de configuration SQL Server**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-141">![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="3213d-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="3213d-142">Dans le volet de navigation, développez l' **instance SQL Server**, développez **configuration du réseau SQL Server**, puis choisissez **protocoles comme \<\>nom d’instance**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-143">![Accéder aux propriétés TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Accéder aux propriétés TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="3213d-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="3213d-144">Dans le volet droit, cliquez avec le bouton droit sur **TCP/IP**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3213d-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="3213d-145">La boîte de dialogue Propriétés TCP/IP s’affiche.</span><span class="sxs-lookup"><span data-stu-id="3213d-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="3213d-146">Sélectionnez l’onglet **adresses IP** . L’onglet adresses IP affiche toutes les adresses IP actives sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="3213d-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="3213d-147">Il s’agit du format IP1, IP2, jusqu’à IPAll, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-148">![Ouvrez les propriétés TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Ouvrez les propriétés TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="3213d-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="3213d-149">Effacez le champ **ports dynamiques TCP** pour toutes les adresses IP.</span><span class="sxs-lookup"><span data-stu-id="3213d-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="3213d-150">Si le champ contient un caractère zéro, cela signifie que SQL Server est à l’écoute sur les ports dynamiques.</span><span class="sxs-lookup"><span data-stu-id="3213d-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="3213d-151">Assurez-vous que ces champs sont effacés et qu’ils ne contiennent pas de zéro.</span><span class="sxs-lookup"><span data-stu-id="3213d-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="3213d-152">Pour l’adresse IP que Lync Server utilisera pour se connecter à la base de données, assurez-vous que l' **option activé** est définie sur **Oui**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-153">![Définissez l’option activé sur Oui pour l’adresse IP correcte.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Définissez l’option activé sur Oui pour l’adresse IP correcte.")</span><span class="sxs-lookup"><span data-stu-id="3213d-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="3213d-154">Dans la section **IPAll** en bas de la boîte de dialogue, entrez le port souhaité dans le champ **port TCP** , comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="3213d-155">Dans cet exemple, nous utilisons le port 50062, mais vous pouvez utiliser n’importe quel port entre 49152 et 65535.</span><span class="sxs-lookup"><span data-stu-id="3213d-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="3213d-156">Il s’agit des ports affectés à une utilisation dynamique et privée, ce qui garantit que vous ne serez pas en conflit avec les autres ports utilisés dans le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3213d-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="3213d-157">![Définir le port dans la section IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Définir le port dans la section IPAll.")</span><span class="sxs-lookup"><span data-stu-id="3213d-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="3213d-158">Choisissez **OK** pour quitter la boîte de dialogue Propriétés TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="3213d-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="3213d-159">Redémarrez l’instance SQL Server en sélectionnant **services SQL Server** dans le volet gauche du gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="3213d-160">Ensuite, cliquez avec le bouton droit sur **nom \<\> de l’instance SQL Server** dans le volet droit, puis sélectionnez **redémarrer**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-161">![Réinitialisez le service SQL Server pour l’instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Réinitialisez le service SQL Server pour l’instance.")</span><span class="sxs-lookup"><span data-stu-id="3213d-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3213d-162">Veillez à mettre à jour vos paramètres de pare-feu afin de prendre en compte le nouveau port SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="3213d-163">**Créer et configurer un alias SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3213d-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="3213d-164">Sélectionnez **Démarrer**, puis **Gestionnaire de configuration SQL Server**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-165">![Icône SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icône SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="3213d-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="3213d-166">Dans le volet de gauche, choisissez l' **instance SQL Server**, puis développez **configuration de la \<version\> du client natif SQL**, puis sélectionnez **alias**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-167">![Alias dans le gestionnaire de configuration SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias dans le gestionnaire de configuration SQL Server.")</span><span class="sxs-lookup"><span data-stu-id="3213d-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="3213d-168">Cliquez avec le bouton droit sur **alias**et sélectionnez **Nouvel alias..**..</span><span class="sxs-lookup"><span data-stu-id="3213d-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="3213d-169">Entrez le **nom**de l’alias, le **numéro de port**, le **protocole**et le **serveur**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-170">![Création d’un alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Création d’un alias")</span><span class="sxs-lookup"><span data-stu-id="3213d-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="3213d-171">Assurez-vous d’entrer le port non standard que vous avez utilisé à l’étape précédente, car il s’agit du port d’écoute de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="3213d-172">Si un alias configuré se connecte à un nom de domaine complet ou à une instance incorrects de SQL Server, désactivez puis réactivez le protocole réseau associé.</span><span class="sxs-lookup"><span data-stu-id="3213d-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="3213d-173">Cette opération efface toutes les informations de connexion mises en cache et autorise le client à se connecter correctement.</span><span class="sxs-lookup"><span data-stu-id="3213d-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="3213d-174">**Créer un enregistrement de ressource CNAMe DNS**</span><span class="sxs-lookup"><span data-stu-id="3213d-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="3213d-175">Connectez-vous à l’ordinateur qui gère DNS.</span><span class="sxs-lookup"><span data-stu-id="3213d-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="3213d-176">Sélectionnez **Démarrer**, puis **Gestionnaire de serveur**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-177">![Ouverture du gestionnaire de serveur](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Ouverture du gestionnaire de serveur")</span><span class="sxs-lookup"><span data-stu-id="3213d-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="3213d-178">Sélectionnez la liste déroulante **Outils** , puis **DNS**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-179">![Ouverture du DNS à partir du gestionnaire de serveur.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Ouverture du DNS à partir du gestionnaire de serveur.")</span><span class="sxs-lookup"><span data-stu-id="3213d-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="3213d-180">Dans le volet gauche, développez le nœud nom du serveur, développez le nœud zones de recherche directes, puis choisissez le domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3213d-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="3213d-181">Cliquez avec le bouton droit sur le domaine, puis sélectionnez **Nouvel alias (CNAME)...**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-182">![Sélection de l’option permettant de créer un nouvel alias CNAMe](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Sélection de l’option permettant de créer un nouvel alias CNAMe")</span><span class="sxs-lookup"><span data-stu-id="3213d-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="3213d-183">Entrez le **nom d’alias** et le nom **de domaine complet (FQDN) de SQL Server**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-184">![Renseignement de la boîte de dialogue nouveau pseudonyme CNAMe.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Renseignement de la boîte de dialogue nouveau pseudonyme CNAMe.")</span><span class="sxs-lookup"><span data-stu-id="3213d-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="3213d-185">Choisissez **OK** pour enregistrer le CNAME et l’afficher dans le Gestionnaire DNS.</span><span class="sxs-lookup"><span data-stu-id="3213d-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="3213d-186">Valider la connectivité de la base de données</span><span class="sxs-lookup"><span data-stu-id="3213d-186">Validate Database Connectivity</span></span>

<span data-ttu-id="3213d-187">Il existe plusieurs façons de s’assurer qu’il fonctionne.</span><span class="sxs-lookup"><span data-stu-id="3213d-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="3213d-188">Vous voulez vous assurer que la base de données SQL Server écoute sur le port spécifié à l’aide de l’alias.</span><span class="sxs-lookup"><span data-stu-id="3213d-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="3213d-189">Une vérification rapide peut être effectuée à l’aide des commandes **netstat** et **Telnet** .</span><span class="sxs-lookup"><span data-stu-id="3213d-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3213d-190">Le client Telnet est une fonctionnalité qui est fournie avec Windows Server, mais qui doit être installée.</span><span class="sxs-lookup"><span data-stu-id="3213d-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="3213d-191">Une fonctionnalité Windows Server peut être installée en ouvrant le gestionnaire de serveur et en sélectionnant Ajouter des rôles et des fonctionnalités dans le menu gérer.</span><span class="sxs-lookup"><span data-stu-id="3213d-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="3213d-192">**Utiliser netstat et Telnet pour vérifier la connectivité de la base de données**</span><span class="sxs-lookup"><span data-stu-id="3213d-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="3213d-193">Sélectionnez **Démarrer**, puis tapez **cmd** pour ouvrir une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="3213d-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="3213d-194">Tapez **netstat-a-f**et confirmez que SQL Server s’exécute avec le port correct, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="3213d-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3213d-195">![Utilisation de netstat pour vérifier le port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilisation de netstat pour vérifier le port.")</span><span class="sxs-lookup"><span data-stu-id="3213d-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="3213d-196">Tapez \*\*telnet \<alias name\> \<port \# \*\* pour confirmer la connexion à l’instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3213d-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="3213d-197">Si la connexion réussit, Telnet se connecte et vous ne devriez pas voir d’erreur.</span><span class="sxs-lookup"><span data-stu-id="3213d-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="3213d-198">Cela indique que l’instance de SQL Server écoute sur le port correct avec l’alias correct.</span><span class="sxs-lookup"><span data-stu-id="3213d-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="3213d-199">Si un problème se présente lors de la connexion à la base de données SQL Server, Telnet affiche une erreur indiquant que la connexion ne peut pas être établie.</span><span class="sxs-lookup"><span data-stu-id="3213d-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="3213d-200">Maintenant que vous avez vérifié la connectivité de base de données sur le serveur de base de données, vous pouvez effectuer la même chose à partir de Lync Server (sur le réseau) et vous assurer qu’aucun pare-feu ne bloque l’accès en cours.</span><span class="sxs-lookup"><span data-stu-id="3213d-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="3213d-201">Conclusion</span><span class="sxs-lookup"><span data-stu-id="3213d-201">Conclusion</span></span>

<span data-ttu-id="3213d-202">Une fois que l’alias SQL Server a été configuré, vous pouvez l’utiliser pour créer une topologie Lync Server 2013 dans l’outil générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3213d-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="3213d-203">Pour plus d’informations sur les topologies, reportez-vous à [la rubrique Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="3213d-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3213d-204">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3213d-204">See Also</span></span>


<span data-ttu-id="3213d-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planification de la sécurité dans Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="3213d-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="3213d-206">Définition et configuration de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3213d-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="3213d-207">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3213d-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

