---
title: Calculatrice de planification de capacité de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="1208e-102">Utiliser le calculateur de planification de capacité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1208e-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1208e-103">_**Dernière modification de la rubrique :** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="1208e-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="1208e-104">Le calculateur Microsoft® Lync™ Server 2013 planification de la capacité est disponible en <http://www.microsoft.com/en-us/download/details.aspx?id=36828>téléchargement à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1208e-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="1208e-105">Il est conçu pour vous aider à déterminer les besoins en matière de serveurs en fonction du nombre d’utilisateurs et de modalités de communication activées au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1208e-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="1208e-106">Vous entrez le profil de votre organisation et la calculatrice fournit des recommandations qui vous aideront à planifier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1208e-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="1208e-107">Les recommandations créées par la calculatrice sont uniquement destinées à la planification.</span><span class="sxs-lookup"><span data-stu-id="1208e-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="1208e-108">La simulation de charge réelle est nécessaire pour garantir que Lync Server 2013 est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="1208e-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="1208e-109">Pour effectuer des tests de stress en utilisant un chargement simulé, utilisez l' [outil de stress et de performances de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="1208e-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="1208e-110">Une fois que vous avez déterminé le profil d’utilisateur et les modalités d’activation pour vos utilisateurs, il est temps d’utiliser la calculatrice pour planifier le nombre de serveurs, de mémoires et de bande passante dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="1208e-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="1208e-111">Cette version du calculateur ne fournit pas de recommandations concernant les spécifications des E/S du disque.</span><span class="sxs-lookup"><span data-stu-id="1208e-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="1208e-112">Cette calculatrice vient compléter [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) et [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="1208e-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="1208e-113">Utilisez le calculateur après avoir consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="1208e-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="1208e-p105">Vous pouvez tirer pleinement parti du calculateur si vous avez des informations précises et détaillées sur votre profil d’utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs pour lesquels la voix est activée, le nombre moyen d’appels par utilisateur et par heure, la durée des appels et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une différence considérable en matière de configuration du serveur. La précision des recommandations créées par le calculateur dépend de celle des informations que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="1208e-p105">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="1208e-117">Utilisation du calculateur de capacité</span><span class="sxs-lookup"><span data-stu-id="1208e-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="1208e-118">La calculatrice est une feuille de calcul Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="1208e-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="1208e-119">Les cellules en couleur orange sont des entrées de votre part.</span><span class="sxs-lookup"><span data-stu-id="1208e-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="1208e-120">Les valeurs par défaut sont tapées (les utilisateurs 80 000 au sein d’un pool avec douze serveurs front-end), mais vous pouvez modifier ces valeurs selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1208e-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="1208e-121">Le modèle d’utilisation contient les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="1208e-121">The usage model contains the following sections.</span></span> <span data-ttu-id="1208e-122">Pour calculer vos exigences de capacité, entrez les données comme décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="1208e-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="1208e-123">**Messagerie instantanée et présence**</span><span class="sxs-lookup"><span data-stu-id="1208e-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="1208e-124">Sous nombre d’utilisateurs, entrez le nombre d’utilisateurs connectés en même temps.</span><span class="sxs-lookup"><span data-stu-id="1208e-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="1208e-125">Ce nombre représente généralement 80 % du nombre total des utilisateurs approvisionnés.</span><span class="sxs-lookup"><span data-stu-id="1208e-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="1208e-126">Le plus souvent, 100 % de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="1208e-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="1208e-127">La valeur par défaut est 80 000.</span><span class="sxs-lookup"><span data-stu-id="1208e-127">The default is 80,000.</span></span>

  - <span data-ttu-id="1208e-128">Nombre moyen de contacts dans la liste de contacts indique le nombre de contacts utilisé pour valider votre configuration système.</span><span class="sxs-lookup"><span data-stu-id="1208e-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="1208e-129">Ce numéro ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="1208e-129">This number is not changeable.</span></span>

<span data-ttu-id="1208e-130">**Voix Entreprise**</span><span class="sxs-lookup"><span data-stu-id="1208e-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="1208e-131">Dans utilisateurs activés pour voix entreprise, tapez le pourcentage d’utilisateurs activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="1208e-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="1208e-132">La valeur par défaut est 60 %.</span><span class="sxs-lookup"><span data-stu-id="1208e-132">The default is 60%.</span></span>

  - <span data-ttu-id="1208e-133">En fonction du nombre d’appels par utilisateur et par heure (PIC), tapez le nombre d’appels par heure que vous vous attendez à ce que l’utilisateur moyen de participer au cours de la période de pointe.</span><span class="sxs-lookup"><span data-stu-id="1208e-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="1208e-134">La valeur par défaut est 4.</span><span class="sxs-lookup"><span data-stu-id="1208e-134">The default is 4.</span></span>

  - <span data-ttu-id="1208e-135">Dans Pourcentage d’appels qui contournent le trafic multimédia, tapez le pourcentage des appels passés par vos utilisateurs qui contourneront le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1208e-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="1208e-136">La valeur par défaut est 65%.</span><span class="sxs-lookup"><span data-stu-id="1208e-136">The default is 65%.</span></span>

  - <span data-ttu-id="1208e-137">Dans Pourcentage d’utilisateurs de la voix participant à des appels UC-PSTN, tapez le pourcentage des appels de votre organisation qui sont des appels téléphoniques UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="1208e-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="1208e-138">La valeur par défaut est 60%</span><span class="sxs-lookup"><span data-stu-id="1208e-138">The default is 60%</span></span>

  - <span data-ttu-id="1208e-139">Dans le pourcentage d’utilisateurs vocaux impliqués dans les appels de communications unifiées, indique le pourcentage d’utilisateurs qui sont activés pour les voix d’entreprise, qui seront activés uniquement pour les appels UC par UC.</span><span class="sxs-lookup"><span data-stu-id="1208e-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="1208e-140">Ce nombre est calculé sur la base de la valeur que vous avez entrée dans le champ Pourcentage d’utilisateurs de la voix activés pour les appels UC-RTC.</span><span class="sxs-lookup"><span data-stu-id="1208e-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="1208e-141">**Conférence**</span><span class="sxs-lookup"><span data-stu-id="1208e-141">**Conferencing**</span></span>

  - <span data-ttu-id="1208e-142">En pourcentage d’utilisateurs dans les conférences simultanées, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences.</span><span class="sxs-lookup"><span data-stu-id="1208e-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="1208e-143">La valeur par défaut est 5 %.</span><span class="sxs-lookup"><span data-stu-id="1208e-143">The default is 5%.</span></span>

  - <span data-ttu-id="1208e-144">Dans le pourcentage de conférences d’une conversation de groupe (pas de voix), tapez le pourcentage de conférences dont les conférences n’impliquent que la messagerie instantanée. autrement dit, il n’y a pas de composant audio.</span><span class="sxs-lookup"><span data-stu-id="1208e-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="1208e-145">La valeur par défaut est 10 %.</span><span class="sxs-lookup"><span data-stu-id="1208e-145">The default is 10%</span></span>

  - <span data-ttu-id="1208e-146">En pourcentage d’utilisateurs à l’aide de la fonction de conférence rendez-vous, tapez le pourcentage de participants concurrents en conférences qui utiliseront la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1208e-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="1208e-147">La valeur par défaut est 15 %.</span><span class="sxs-lookup"><span data-stu-id="1208e-147">The default is 15%.</span></span>

  - <span data-ttu-id="1208e-148">Dans pourcentage de conférences utilisant la voix, tapez le pourcentage de conférences qui incluront un composant audio.</span><span class="sxs-lookup"><span data-stu-id="1208e-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="1208e-149">Si 20 % de vos conférences vocales incluront également de la vidéo standard, activez la case à cocher Vidéo incluse (pas de multi-vue).</span><span class="sxs-lookup"><span data-stu-id="1208e-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="1208e-150">Si 20 % de vos conférences incluront également la vidéo multi-vue, activez la case à cocher Multi-vue incluse.</span><span class="sxs-lookup"><span data-stu-id="1208e-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="1208e-151">Si 50 % de vos conférences vocales incluront également le partage d’application, activez la case à cocher Partage d’application inclus.</span><span class="sxs-lookup"><span data-stu-id="1208e-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="1208e-152">Si 20% de vos conférences vocales incluent des téléchargements de données, tels que Microsoft PowerPoint® présentations, activez la case à cocher inclure les conférences Web.</span><span class="sxs-lookup"><span data-stu-id="1208e-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="1208e-153">**Mobilité**</span><span class="sxs-lookup"><span data-stu-id="1208e-153">**Mobility**</span></span>

  - <span data-ttu-id="1208e-154">Dans pourcentage d’utilisateurs activés pour la mobilité, tapez le pourcentage d’utilisateurs qui seront activés pour se connecter à Lync Server à l’aide d’appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="1208e-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="1208e-155">La valeur par défaut est 40 %.</span><span class="sxs-lookup"><span data-stu-id="1208e-155">The default is 40%.</span></span>

<span data-ttu-id="1208e-156">Lorsque vous avez entré toutes les informations nécessaires, le calculateur de capacité évalue votre configuration requise.</span><span class="sxs-lookup"><span data-stu-id="1208e-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="1208e-157">Les cellules jaunes montrent des valeurs calculées pour le processeur, la mémoire et les exigences de bande passante en fonction des tests exécutés dans Lync Server 2013 performance Labs.</span><span class="sxs-lookup"><span data-stu-id="1208e-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="1208e-158">Les nombres sont fournis dans le cadre d’une instruction, et aucune variante unique n’est testée et validée.</span><span class="sxs-lookup"><span data-stu-id="1208e-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="1208e-159">Les valeurs suivantes sont calculées :</span><span class="sxs-lookup"><span data-stu-id="1208e-159">The following values are calculated:</span></span>

  - <span data-ttu-id="1208e-160">PROCESSEUR frontal : pourcentage d’utilisation de l’UC si le chargement complet a été géré par un serveur frontal de mêmes spécifications que le serveur utilisé dans les tests Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1208e-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="1208e-161">Réseau (Mbits/s) : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.</span><span class="sxs-lookup"><span data-stu-id="1208e-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="1208e-162">Mémoire (Go) : mémoire requise en giga-octets (Go) pour la charge de travail correspondante.</span><span class="sxs-lookup"><span data-stu-id="1208e-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="1208e-163">Les cellules vertes indiquent les recommandations pour le modèle d’utilisation que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="1208e-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="1208e-164">Nombre total de serveurs frontaux : le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Lync Server 2013 avec deux processeurs, avec le cœur hexadécimal, avec 2 260 mégacycles.</span><span class="sxs-lookup"><span data-stu-id="1208e-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="1208e-165">Il est recommandé d’activer l’hyperthreading. Il a été démontré que cette technologie améliore les performances des serveurs prenant en charge le son et la vidéo.</span><span class="sxs-lookup"><span data-stu-id="1208e-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="1208e-166">Serveurs Edge : le nombre de serveurs Edge requis, en fonction de 30% de tous les utilisateurs concurrents qui communiquent par le biais des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="1208e-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="1208e-167">Ce pourcentage ne peut pas être modifié dans la calculatrice.</span><span class="sxs-lookup"><span data-stu-id="1208e-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="1208e-168">Magasin pour l’archivage/l’enregistrement des détails des appels/les services de qualité de l’expérience (QoE) : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, si celles-ci sont activées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1208e-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="1208e-169">Serveur de base de données principal requis (pools requis) : nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1208e-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="1208e-170">Dans la ligne en regard de Nombre total de serveurs frontaux, des informations supplémentaires sont fournies sur la charge sur vos serveurs et le réseau pour les charges de travail combinées.</span><span class="sxs-lookup"><span data-stu-id="1208e-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="1208e-171">Charge processeur moyenne : utilisation moyenne du processeur par serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1208e-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="1208e-172">Réseau (en Mbits/s) : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="1208e-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="1208e-173">Mémoire (en Go) : mémoire en giga-octets requise pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1208e-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="1208e-174">Ajustement de vos processeurs</span><span class="sxs-lookup"><span data-stu-id="1208e-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="1208e-175">Tous les chiffres relatifs à l’utilisation du processeur dans la feuille de calcul partent du principe que chaque serveur est équipé d’un biprocesseur, hexa-cœur avec 2,26 GHz, 32 Go de mémoire au minimum, et 8 (ou plus) disques durs d’une vitesse de 10 000 RPM avec au moins 72 Go d’espace disponible.</span><span class="sxs-lookup"><span data-stu-id="1208e-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="1208e-176">Si vos serveurs ont d’autres processeurs, vous pouvez modifier les chiffres pour les adapter à votre matériel.</span><span class="sxs-lookup"><span data-stu-id="1208e-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

