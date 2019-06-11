---
title: Définition et configuration d’un pool frontal ou d’un serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="a23eb-102">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a23eb-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a23eb-103">_**Dernière modification de la rubrique:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="a23eb-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="a23eb-104">Cette procédure ne nécessite pas d’appartenance à un administrateur local ou à un groupe de domaines privilégiés.</span><span class="sxs-lookup"><span data-stu-id="a23eb-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="a23eb-105">Vous devez vous connecter à un ordinateur en tant qu’utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="a23eb-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="a23eb-106">Si vous déployez un serveur d’entreprise, un nombre minimum de serveurs frontaux dans un pool doit être en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="a23eb-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="a23eb-107">Le tableau suivant récapitule ces exigences.</span><span class="sxs-lookup"><span data-stu-id="a23eb-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a23eb-108">Nombre total de serveurs frontaux de la liste</span><span class="sxs-lookup"><span data-stu-id="a23eb-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="a23eb-109">Nombre de serveurs devant être exécutés pour que le pool soit opérationnel</span><span class="sxs-lookup"><span data-stu-id="a23eb-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a23eb-110">1-2</span><span class="sxs-lookup"><span data-stu-id="a23eb-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="a23eb-111">1</span><span class="sxs-lookup"><span data-stu-id="a23eb-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23eb-112">3-4</span><span class="sxs-lookup"><span data-stu-id="a23eb-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="a23eb-113">2</span><span class="sxs-lookup"><span data-stu-id="a23eb-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23eb-114">5-6</span><span class="sxs-lookup"><span data-stu-id="a23eb-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="a23eb-115">3</span><span class="sxs-lookup"><span data-stu-id="a23eb-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23eb-116">7-8</span><span class="sxs-lookup"><span data-stu-id="a23eb-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="a23eb-117">4</span><span class="sxs-lookup"><span data-stu-id="a23eb-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23eb-118">9-10</span><span class="sxs-lookup"><span data-stu-id="a23eb-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="a23eb-119">5</span><span class="sxs-lookup"><span data-stu-id="a23eb-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23eb-120">11-12</span><span class="sxs-lookup"><span data-stu-id="a23eb-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="a23eb-121">6</span><span class="sxs-lookup"><span data-stu-id="a23eb-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="a23eb-122">Pour Lync Server 2013, chaque fois que vous ajoutez ou supprimez un serveur frontal de la liste, vous devez redémarrer les services.</span><span class="sxs-lookup"><span data-stu-id="a23eb-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="a23eb-123">La suppression et l’ajout de serveurs doivent être effectuées en tant qu’opérations séparées.</span><span class="sxs-lookup"><span data-stu-id="a23eb-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="a23eb-124">Par exemple, si vous envisagez d’ajouter deux serveurs frontaux et de supprimer deux serveurs frontaux, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="a23eb-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="a23eb-125">Supprimez les deux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="a23eb-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="a23eb-126">Publiez et réactivez la topologie.</span><span class="sxs-lookup"><span data-stu-id="a23eb-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="a23eb-127">Redémarrer les services</span><span class="sxs-lookup"><span data-stu-id="a23eb-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="a23eb-128">Ajoutez les deux serveurs front-end.</span><span class="sxs-lookup"><span data-stu-id="a23eb-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="a23eb-129">Publiez et réactivez la topologie.</span><span class="sxs-lookup"><span data-stu-id="a23eb-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="a23eb-130">Redémarrez les services.</span><span class="sxs-lookup"><span data-stu-id="a23eb-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="a23eb-131">Après avoir défini votre topologie, utilisez la procédure suivante pour définir un pool frontal pour votre site.</span><span class="sxs-lookup"><span data-stu-id="a23eb-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="a23eb-132">Pour plus d’informations sur la définition de la topologie, voir [définir et configurer une topologie dans le générateur de topologies pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="a23eb-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="a23eb-133">Pour définir un pool frontal</span><span class="sxs-lookup"><span data-stu-id="a23eb-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="a23eb-134">Dans l’Assistant définir un nouveau pool frontal, dans la page **définir le nouveau pool frontal** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="a23eb-135">Dans la page **définir le nom de domaine complet du pool frontal** , entrez un nom de domaine complet (FQDN) pour le pool que vous \*\*\*\* êtes en train de créer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="a23eb-136">Dans la page **définir les ordinateurs de ce pool** , entrez un nom de domaine complet pour le premier serveur frontal de la liste, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="a23eb-137">Répétez cette étape pour tous les ordinateurs que vous voulez ajouter à la liste, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="a23eb-138">Dans la page **Sélectionner des fonctionnalités** , activez les cases à cocher des fonctionnalités que vous voulez inclure dans ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="a23eb-139">Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher **conférences** pour autoriser la messagerie instantanée à plusieurs éléments, mais pas la sélection des conférences rendez **-vous (RTC)**, **voix entreprise**ou \*\* \*\*Cases à cocher contrôle d’admission des appels, car elles représentent les fonctionnalités de conférence vocale, vidéo et de collaboration.</span><span class="sxs-lookup"><span data-stu-id="a23eb-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="a23eb-140">**Conférences**   cette sélection permet d’obtenir une gamme étendue de fonctionnalités, notamment:</span><span class="sxs-lookup"><span data-stu-id="a23eb-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="a23eb-141">Messagerie instantanée avec plus de deux parties dans une session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="a23eb-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="a23eb-142">Conférences, qui comprennent la collaboration sur des documents, le partage d’application et le partage de bureau.</span><span class="sxs-lookup"><span data-stu-id="a23eb-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="a23eb-143">Une conférence a/V, qui permet aux utilisateurs d’effectuer des conférences audio/vidéo (A/V) en temps réel sans recourir à des services externes tels que le service Live Meeting ou un pont audio tiers.</span><span class="sxs-lookup"><span data-stu-id="a23eb-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="a23eb-144">**Les conférences**   rendez-vous (RTC) permettent aux utilisateurs d’accéder à la partie audio d’une conférence 2013 Server Lync à l’aide d’un téléphone réseau téléphonique commuté (PSTN) sans nécessiter un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="a23eb-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="a23eb-145">**Enterprise voix**   entreprise voix est la solution VoIP (Voice over IP) dans Lync Server 2013, qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="a23eb-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="a23eb-146">Vous déploierez cette fonctionnalité si vous envisagez d’utiliser Lync Server 2013 pour les appels vocaux, la messagerie vocale et d’autres fonctions qui utilisent un appareil matériel ou un client logiciel.</span><span class="sxs-lookup"><span data-stu-id="a23eb-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="a23eb-147">**Le contrôle d’admission des appels (CAC)**   CAC détermine, en fonction de la bande passante disponible sur le réseau, s’il est possible d’établir des sessions de communication en temps réel telles que des appels vocaux ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="a23eb-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="a23eb-148">Si vous avez déployé uniquement la messagerie instantanée et la présence, CAC n’est pas nécessaire, car aucune de ces deux fonctionnalités n’utilise le CAC.</span><span class="sxs-lookup"><span data-stu-id="a23eb-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="a23eb-149">\*\*\*\* L’archivage de l’archivage vous permet d’archiver le contenu du message instantané, le contenu de la réunion ou les deux envoyés via Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="a23eb-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="a23eb-150">**La surveillance**   de Analysis Server vous permet de recueillir des données numériques qui décrivent la qualité multimédia sur votre réseau et vos points de terminaison, des informations sur l’utilisation des appels VoIP, des messages instantanés, des conversations par messagerie instantanée, des réunions, du partage d’applications et du fichier. transferts et informations d’erreur et de dépannage pour les appels en échec.</span><span class="sxs-lookup"><span data-stu-id="a23eb-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a23eb-151">Si vous voulez activer le CAC dans votre déploiement, il est nécessaire d’activer le service CAC dans exactement un pool par site central.</span><span class="sxs-lookup"><span data-stu-id="a23eb-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="a23eb-152">Le CAC est recommandé si vous déployez des fonctions vocales ou des conférences A/V.</span><span class="sxs-lookup"><span data-stu-id="a23eb-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="a23eb-153">Le tableau suivant répertorie les fonctionnalités disponibles (haut) et les fonctions proposées aux utilisateurs (à gauche).</span><span class="sxs-lookup"><span data-stu-id="a23eb-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="a23eb-154">Les sélections du tableau sont celles que vous devez sélectionner pour activer ces fonctionnalités pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a23eb-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="a23eb-155">Conférence</span><span class="sxs-lookup"><span data-stu-id="a23eb-155">Conferencing</span></span></th>
    <th><span data-ttu-id="a23eb-156">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="a23eb-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="a23eb-157">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="a23eb-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="a23eb-158">Contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="a23eb-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a23eb-159">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="a23eb-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="a23eb-160">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a23eb-161">Conférence</span><span class="sxs-lookup"><span data-stu-id="a23eb-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="a23eb-162">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-162">X</span></span></p></td>
    <td><p><span data-ttu-id="a23eb-163">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a23eb-164">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="a23eb-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="a23eb-165">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-165">X</span></span></p></td>
    <td><p><span data-ttu-id="a23eb-166">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="a23eb-167">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a23eb-168">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="a23eb-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="a23eb-169">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-169">X</span></span></p></td>
    <td><p><span data-ttu-id="a23eb-170">X</span><span class="sxs-lookup"><span data-stu-id="a23eb-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="a23eb-171">Dans la page **Sélectionner des rôles de serveur** colocalisés, vous pouvez Collocate le serveur de médiation sur le serveur frontal ou le déployer en tant que serveur autonome.</span><span class="sxs-lookup"><span data-stu-id="a23eb-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="a23eb-172">Vous pouvez collocate le serveur de médiation sur le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="a23eb-173">Si vous envisagez de collocate le serveur de médiation sur le pool frontal Enterprise Edition, assurez-vous que la case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="a23eb-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="a23eb-174">Le rôle serveur sera déployé sur les serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="a23eb-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="a23eb-175">Si vous envisagez de déployer le serveur de médiation en tant que serveur autonome, décochez la case correspondante.</span><span class="sxs-lookup"><span data-stu-id="a23eb-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="a23eb-176">Vous déploierez le serveur de médiation dans une étape de déploiement séparée après le déploiement complet du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a23eb-177">Nous vous recommandons de collocate le serveur de médiation, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="a23eb-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="a23eb-178">Pour plus d’informations sur la prise en charge des serveurs de médiation autonomes ou autonomes, voir <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">composants et topologies du serveur de médiation dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a23eb-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="a23eb-179">Les **rôles serveur Associate avec cette page de pool frontal** vous permettent de définir et d’associer des rôles de serveur avec le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="a23eb-180">Le rôle suivant est disponible :</span><span class="sxs-lookup"><span data-stu-id="a23eb-180">The following role is available:</span></span>
    
    <span data-ttu-id="a23eb-181">**Activer un pool**   Edge définit et associe un serveur Edge unique ou un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="a23eb-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="a23eb-182">Un serveur Edge facilite la communication et la collaboration entre les utilisateurs au sein de l’organisation et les personnes qui travaillent en dehors de celle-ci, notamment les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="a23eb-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="a23eb-183">Vous pouvez utiliser deux scénarios possibles pour déployer et associer les rôles de serveur:</span><span class="sxs-lookup"><span data-stu-id="a23eb-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="a23eb-184">Dans le premier scénario, vous définissez une nouvelle topologie pour une nouvelle installation.</span><span class="sxs-lookup"><span data-stu-id="a23eb-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="a23eb-185">Vous pouvez aborder l’installation de deux manières:</span><span class="sxs-lookup"><span data-stu-id="a23eb-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="a23eb-186">Laissez la case à cocher désactivée et continuez de définir la topologie.</span><span class="sxs-lookup"><span data-stu-id="a23eb-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="a23eb-187">Une fois les rôles serveur frontal et principal publiés, configurés et testés, vous pouvez réexécuter le Générateur de topologies afin de les ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="a23eb-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="a23eb-188">Cette stratégie vous permet de tester le pool frontal et le serveur exécutant SQL Server sans complications supplémentaires provenant de rôles supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a23eb-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="a23eb-189">Une fois les tests initiaux réalisés, vous pouvez réexécuter le Générateur de topologies afin de sélectionner les rôles à déployer.</span><span class="sxs-lookup"><span data-stu-id="a23eb-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="a23eb-190">Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a23eb-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="a23eb-191">Dans le scénario 2, vous disposez d’un déploiement existant et votre infrastructure est prête pour de nouveaux rôles ou vous devez associer des rôles existants à un nouveau serveur frontal:</span><span class="sxs-lookup"><span data-stu-id="a23eb-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="a23eb-192">Dans ce cas, vous devez sélectionner les rôles que vous souhaitez déployer ou associer au nouveau serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="a23eb-193">Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="a23eb-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="a23eb-194">Dans la page **définir le SQL Store** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="a23eb-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a23eb-195">Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="a23eb-196">Pour définir une nouvelle instance SQL Server pour stocker des informations de pool, cliquez sur **nouveau** , puis spécifiez le **nom de domaine complet SQL Server**dans la boîte de dialogue **définir un nouveau SQL Store** .</span><span class="sxs-lookup"><span data-stu-id="a23eb-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="a23eb-197">Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée**, puis spécifiez le nom de l’instance.</span><span class="sxs-lookup"><span data-stu-id="a23eb-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="a23eb-198">Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="a23eb-199">Pour utiliser la mise en miroir SQL, sélectionnez **activer la mise en miroir SQL** et sélectionnez une instance existante ou créez une nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="a23eb-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="a23eb-200">Dans la page **définir le partage de fichiers** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="a23eb-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a23eb-201">Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="a23eb-202">Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers**. Dans la zone **Nom de domaine complet du serveur de fichiers**, entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="a23eb-203">Le partage de fichiers pour Lync Server 2013 ne se trouve pas sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="a23eb-204">Notez que dans cet exemple, le partage de fichiers a été localisé sur le serveur principal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a23eb-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="a23eb-205">Il est possible qu’il ne s’agit pas d’un emplacement optimal pour les besoins de votre organisation, et qu’un serveur de fichiers soit un meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="a23eb-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="a23eb-206">Vous pouvez définir le partage de fichiers sans avoir à le créer.</span><span class="sxs-lookup"><span data-stu-id="a23eb-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="a23eb-207">Vous devrez créer le partage de fichiers à l’emplacement défini avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="a23eb-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="a23eb-208">Dans la page **spécifier l’URL du service Web** , effectuez l’une des opérations suivantes ou les deux:</span><span class="sxs-lookup"><span data-stu-id="a23eb-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="a23eb-209">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="a23eb-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="a23eb-210">Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="a23eb-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="a23eb-211">Si vous avez plusieurs pools frontal ou serveur principal, le nom de domaine complet des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="a23eb-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="a23eb-212">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="a23eb-213">Si vous configurez l’équilibrage de charge DNS, activez la case à cocher **remplacer le FQDN du pool de services Web interne** , entrez l’URL de base interne (qui doit être différente de celle du pool de nom\<de domaine complet\>, par exemple, l’URL de base) dans \*\* URL de base interne\*\*.</span><span class="sxs-lookup"><span data-stu-id="a23eb-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="a23eb-214">Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de directeurs.</span><span class="sxs-lookup"><span data-stu-id="a23eb-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="a23eb-215"><STRONG>Utilisez uniquement les caractères standard</STRONG> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous définissez les URL ou les noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="a23eb-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="a23eb-216">N’utilisez pas les caractères ou traits de soulignement Unicode.</span><span class="sxs-lookup"><span data-stu-id="a23eb-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a23eb-217">Souvent, les caractères non standard dans une URL ou un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand l’URL ou le FQDN doit être assigné au nom ou à l’autre nom de l’objet dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="a23eb-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="a23eb-218">Si vous le souhaitez, entrez l’URL de base externe dans **URL de base externe**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="a23eb-219">Pour différencier votre nom de domaine interne, entrez l’URL de base externe.</span><span class="sxs-lookup"><span data-stu-id="a23eb-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="a23eb-220">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a23eb-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="a23eb-221">Vous devez définir l’URL en utilisant le nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a23eb-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="a23eb-222">Cela est également important dans le cas d’un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a23eb-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="a23eb-223">Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a23eb-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="a23eb-224">La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="a23eb-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a23eb-225">Pour utiliser l’équilibrage de charge DNS, vous devez créer les enregistrements DNS appropriés.</span><span class="sxs-lookup"><span data-stu-id="a23eb-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="a23eb-226">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurer le DNS pour l’équilibrage de charge dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a23eb-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="a23eb-227">Si vous avez sélectionné l’option **conférences** dans la page **Sélectionner des fonctionnalités** , dans la page **Sélectionner un serveur Office Web Apps** , sélectionnez **associer le pool à un serveur Office Web Apps** , puis cliquez sur **nouveau** (ou sélectionnez une application Office Web Apps existante). Serveur dans la liste déroulante).</span><span class="sxs-lookup"><span data-stu-id="a23eb-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="a23eb-228">Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="a23eb-229">Si Office Web Apps Server est installé en local et dans la même zone réseau que Lync Server 2013, l’option **Office Web Apps Server déployée sur un réseau externe (c’est-à-dire le périmètre/Internet)** ne doit pas être sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a23eb-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="a23eb-230">Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a23eb-231">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configuration de l’intégration avec Office Web Apps Server et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a23eb-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="a23eb-232">Dans la page **définir le SQL Store** d’archivage, sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="a23eb-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="a23eb-233">Dans la page **définir la surveillance du SQL Store** , sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour le stockage des données associées aux données d’analyse.</span><span class="sxs-lookup"><span data-stu-id="a23eb-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="a23eb-234">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-234">Click **Next**.</span></span> <span data-ttu-id="a23eb-235">Si vous avez défini d’autres serveurs de rôles sur la page **associer des rôles de serveur à cette liste frontale** , des pages d’assistant de configuration de rôles distinctes s’ouvrent pour vous permettre de configurer les rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="a23eb-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="a23eb-236">Pour plus d’informations, reportez-vous aux rubriques suivantes:</span><span class="sxs-lookup"><span data-stu-id="a23eb-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="a23eb-237">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a23eb-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="a23eb-238">Si vous n’avez pas sélectionné de rôles serveur supplémentaires à configurer et déployer ou lorsque vous avez terminé la configuration des serveurs de rôles supplémentaires, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a23eb-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

