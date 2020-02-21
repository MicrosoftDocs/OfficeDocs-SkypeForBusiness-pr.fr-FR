---
title: Calculatrice de planification de capacité Lync Server 2013
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
ms.openlocfilehash: b920f7fd0325c3232abb5670a2da66fc98352d38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="f7ebe-102">Utilisation de la calculatrice de planification de la capacité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7ebe-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7ebe-103">_**Dernière modification de la rubrique :** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="f7ebe-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="f7ebe-104">La calculatrice de planification de capacité Microsoft® Lync™ Server 2013 peut être téléchargée à l’adresse <https://www.microsoft.com/download/details.aspx?id=36828>.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="f7ebe-105">Elle est conçue pour vous aider à déterminer les exigences de serveur en fonction du nombre d’utilisateurs et de modalités de communication activés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="f7ebe-106">Vous entrez le profil de votre organisation et la calculatrice fournit des recommandations pour vous aider à planifier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="f7ebe-107">Les recommandations créées par la calculatrice sont uniquement destinées à la planification.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="f7ebe-108">La simulation de charge réelle est nécessaire pour s’assurer que Lync Server 2013 est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="f7ebe-109">Pour effectuer des tests de contrainte sous une charge simulée, utilisez l' [outil de contrainte et de performances de Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="f7ebe-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="f7ebe-110">Une fois que vous avez déterminé votre profil utilisateur et les modalités que vous souhaitez activer pour vos utilisateurs, il est temps d’utiliser la calculatrice pour planifier le nombre de serveurs, la mémoire et la bande passante dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="f7ebe-111">Cette version de la calculatrice ne fournit pas d’instructions pour les besoins en e/s disque.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="f7ebe-112">Cette calculatrice complète [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) et [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="f7ebe-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="f7ebe-113">Utilisez la calculatrice une fois que vous avez consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="f7ebe-114">Vous pouvez tirer le meilleur parti de la calculatrice si vous disposez d’informations précises et détaillées sur votre profil utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="f7ebe-115">Par exemple, le pourcentage d’utilisateurs à extension vocale, le nombre moyen d’appels par utilisateur et par heure, la durée de l’appel et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une très grande différence en termes de serveur.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="f7ebe-116">La précision des recommandations créées par la calculatrice dépend de la précision des informations que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="f7ebe-117">Utilisation de la calculatrice de capacité</span><span class="sxs-lookup"><span data-stu-id="f7ebe-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="f7ebe-118">La calculatrice est une feuille de calcul Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="f7ebe-119">Les cellules colorées en orange sont destinées à des fins de saisie.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="f7ebe-120">Les valeurs par défaut sont entrées (80 000 utilisateurs dans un pool avec douze serveurs frontaux), mais vous pouvez modifier ces valeurs en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="f7ebe-121">Le modèle d’utilisation contient les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-121">The usage model contains the following sections.</span></span> <span data-ttu-id="f7ebe-122">Pour calculer vos besoins en capacité, entrez les données comme décrit :</span><span class="sxs-lookup"><span data-stu-id="f7ebe-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="f7ebe-123">**Messagerie instantanée et présence**</span><span class="sxs-lookup"><span data-stu-id="f7ebe-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="f7ebe-124">Sous nombre d’utilisateurs, tapez le nombre d’utilisateurs qui seront connectés simultanément.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="f7ebe-125">Ce nombre est généralement de 80% du nombre total d’utilisateurs configurés.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="f7ebe-126">Dans la plupart des cas, 100% de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="f7ebe-127">La valeur par défaut est 80 000.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-127">The default is 80,000.</span></span>

  - <span data-ttu-id="f7ebe-128">Nombre moyen de contacts dans la liste de contacts indique le nombre de contacts que nous utilisons pour valider la configuration système requise.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="f7ebe-129">Ce numéro ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-129">This number is not changeable.</span></span>

<span data-ttu-id="f7ebe-130">**Voix Entreprise**</span><span class="sxs-lookup"><span data-stu-id="f7ebe-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="f7ebe-131">Dans utilisateurs activés pour voix entreprise, tapez le pourcentage de vos utilisateurs qui sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f7ebe-132">La valeur par défaut est 60%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-132">The default is 60%.</span></span>

  - <span data-ttu-id="f7ebe-133">En nombre moyen d’appels par utilisateur et par heure (PIC), tapez le nombre d’appels par heure pendant lesquels l’utilisateur moyen doit participer pendant les périodes de charge maximale.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="f7ebe-134">La valeur par défaut est 4.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-134">The default is 4.</span></span>

  - <span data-ttu-id="f7ebe-135">Dans pourcentage des appels qui utilisent la déviation du trafic multimédia, tapez le pourcentage d’appels passés par vos utilisateurs pour contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="f7ebe-136">La valeur par défaut est 65%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-136">The default is 65%.</span></span>

  - <span data-ttu-id="f7ebe-137">Dans pourcentage des utilisateurs vocaux impliqués dans les appels UC-PSTN, tapez le pourcentage des appels de votre organisation qui sont des appels de téléphone de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="f7ebe-138">La valeur par défaut est 60%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-138">The default is 60%</span></span>

  - <span data-ttu-id="f7ebe-139">Pourcentage d’utilisateurs vocaux impliqués dans les appels UC-UC indique le pourcentage d’utilisateurs activés pour voix entreprise qui seront activés uniquement pour les appels UC-UC.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="f7ebe-140">Ce nombre est calculé en fonction de ce que vous entrez pour le pourcentage d’utilisateurs vocaux activé pour les appels UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="f7ebe-141">**Vidéoconférence**</span><span class="sxs-lookup"><span data-stu-id="f7ebe-141">**Conferencing**</span></span>

  - <span data-ttu-id="f7ebe-142">Dans pourcentage d’utilisateurs dans des conférences simultanées, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="f7ebe-143">La valeur par défaut est 5%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-143">The default is 5%.</span></span>

  - <span data-ttu-id="f7ebe-144">Dans pourcentage de conférences avec la messagerie instantanée de groupe uniquement (pas de voix), tapez le pourcentage de conférences dont les conférences impliquent uniquement la messagerie instantanée ; autrement dit, il n’y a pas de composant audio.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="f7ebe-145">La valeur par défaut est 10%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-145">The default is 10%</span></span>

  - <span data-ttu-id="f7ebe-146">Dans pourcentage des utilisateurs qui utilisent la Conférence rendez-vous, tapez le pourcentage de participants simultanés dans les conférences qui utiliseront la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="f7ebe-147">La valeur par défaut est 15%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-147">The default is 15%.</span></span>

  - <span data-ttu-id="f7ebe-148">Dans pourcentage de conférences à l’aide de la voix, tapez le pourcentage de conférences qui comprendront un composant audio.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="f7ebe-149">Si 20% de vos conférences vocales incluent également une vidéo normale, activez la case à cocher y compris la vidéo (pas de multi-vue).</span><span class="sxs-lookup"><span data-stu-id="f7ebe-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="f7ebe-150">Si 20% de vos conférences incluent également la vidéo multi-vue, activez la case à cocher incluant plusieurs vues.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="f7ebe-151">Si 50% de vos conférences vocales incluent également le partage d’application, activez la case à cocher inclure le partage d’applications.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="f7ebe-152">Si 20% de vos conférences vocales incluent des téléchargements de données, tels que des présentations Microsoft PowerPoint®, activez la case à cocher inclure la conférence Web.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="f7ebe-153">**Mobilité**</span><span class="sxs-lookup"><span data-stu-id="f7ebe-153">**Mobility**</span></span>

  - <span data-ttu-id="f7ebe-154">Dans pourcentage d’utilisateurs activés pour la mobilité, tapez le pourcentage de vos utilisateurs qui seront activés pour se connecter à Lync Server à l’aide d’appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="f7ebe-155">La valeur par défaut est 40%.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-155">The default is 40%.</span></span>

<span data-ttu-id="f7ebe-156">Une fois que vous avez entré toutes les informations nécessaires, la calculatrice de capacité estime votre configuration requise.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="f7ebe-157">Les cellules jaunes affichent les valeurs calculées pour l’UC, la mémoire et les besoins en bande passante en fonction des tests effectués dans les laboratoires de performance Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="f7ebe-158">Les numéros sont fournis en tant qu’indications, et toutes les variantes ne sont pas testées et validées.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="f7ebe-159">Les valeurs suivantes sont calculées :</span><span class="sxs-lookup"><span data-stu-id="f7ebe-159">The following values are calculated:</span></span>

  - <span data-ttu-id="f7ebe-160">PROCESSEUR frontal : pourcentage d’utilisation de l’UC si la totalité de la charge a été gérée par un serveur frontal des mêmes spécifications que le serveur utilisé dans les tests Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="f7ebe-161">Réseau en Mbits/s : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="f7ebe-162">Mémoire en Go : mémoire requise en gigaoctets (Go) pour la charge de travail correspondante.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="f7ebe-163">Les cellules vertes affichent des recommandations pour le modèle d’utilisation que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="f7ebe-164">Nombre total de serveurs frontaux : le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Lync Server 2013 avec deux processeurs, hex-Core, avec 2 260 mégacycles.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="f7ebe-165">Notez que l’activation de l’hyperthreading est recommandée et a été prouvée pour améliorer les performances des serveurs qui prennent en charge l’audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="f7ebe-166">Serveurs Edge : nombre de serveurs Edge requis, basé sur 30% de tous les utilisateurs simultanés communiquant via les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="f7ebe-167">Ce pourcentage ne peut pas être modifié dans la calculatrice.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="f7ebe-168">Magasin d’archivage/d’appel des détails d’enregistrement/de qualité de l’expérience : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, s’ils sont activés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="f7ebe-169">Serveur de base de données principal requis (pools requis) : nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="f7ebe-170">En outre, dans la ligne en regard de serveurs frontaux totaux, des informations supplémentaires sont fournies sur la charge de vos serveurs et de votre réseau pour toutes les charges de travail associées.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="f7ebe-171">Charge moyenne de l’UC : utilisation moyenne du processeur par serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="f7ebe-172">Réseau en Mbits/s : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="f7ebe-173">Mémoire en Go : mémoire, en gigaoctets, requise pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="f7ebe-174">Ajustement pour vos processeurs</span><span class="sxs-lookup"><span data-stu-id="f7ebe-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="f7ebe-175">Tous les chiffres d’utilisation du processeur de la feuille de calcul partent du principe que chaque serveur est doté d’un double processeur, d’un cœur avec 2,26 GHz, d’au moins 32 Go de mémoire et de 8 disques durs 10 000-RPM avec au moins 72 Go d’espace disque disponible.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="f7ebe-176">Si vos serveurs ont des processeurs différents, vous pouvez ajuster les chiffres pour qu’ils correspondent à votre matériel.</span><span class="sxs-lookup"><span data-stu-id="f7ebe-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

