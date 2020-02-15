---
title: Définition et configuration d’un pool frontal ou d’un serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35c49ab232bd69184191ab841431e6c80eca20a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="dc4cc-102">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc4cc-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc4cc-103">_**Dernière modification de la rubrique :** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="dc4cc-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="dc4cc-p101">Pour effectuer cette procédure, il n’est pas nécessaire d’appartenir à un groupe d’administrateurs local ou de domaines privilégiés. Vous devez simplement ouvrir une session sur un ordinateur en tant qu’utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="dc4cc-106">Si vous déployez un serveur d’entreprise, un nombre minimal de serveurs frontaux dans un pool doit être en cours d’exécution en permanence.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="dc4cc-107">Le tableau suivant résume ces exigences :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc4cc-108">Nombre total de serveurs frontaux dans le pool</span><span class="sxs-lookup"><span data-stu-id="dc4cc-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="dc4cc-109">Nombre de serveurs devant s’exécuter pour que le pool soit opérationnel</span><span class="sxs-lookup"><span data-stu-id="dc4cc-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc4cc-110">1-2</span><span class="sxs-lookup"><span data-stu-id="dc4cc-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="dc4cc-111">1 </span><span class="sxs-lookup"><span data-stu-id="dc4cc-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4cc-112">3-4</span><span class="sxs-lookup"><span data-stu-id="dc4cc-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="dc4cc-113">2 </span><span class="sxs-lookup"><span data-stu-id="dc4cc-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4cc-114">5-6</span><span class="sxs-lookup"><span data-stu-id="dc4cc-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="dc4cc-115">3 </span><span class="sxs-lookup"><span data-stu-id="dc4cc-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4cc-116">7-8</span><span class="sxs-lookup"><span data-stu-id="dc4cc-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="dc4cc-117">4 </span><span class="sxs-lookup"><span data-stu-id="dc4cc-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4cc-118">9-10</span><span class="sxs-lookup"><span data-stu-id="dc4cc-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="dc4cc-119">5 </span><span class="sxs-lookup"><span data-stu-id="dc4cc-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4cc-120">11-12</span><span class="sxs-lookup"><span data-stu-id="dc4cc-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="dc4cc-121">6 </span><span class="sxs-lookup"><span data-stu-id="dc4cc-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="dc4cc-122">Pour Lync Server 2013, chaque fois que vous ajoutez ou supprimez un serveur frontal du pool, vous devez redémarrer les services.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="dc4cc-123">La suppression et l’ajout de serveurs doivent être effectuées séparément.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="dc4cc-124">Par exemple, si vous envisagez d’ajouter deux serveurs frontaux et de supprimer deux serveurs frontaux, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="dc4cc-125">Supprimez les deux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc4cc-126">Publiez et réactivez la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc4cc-127">Redémarrez les services.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="dc4cc-128">Ajoutez les deux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc4cc-129">Publiez et réactivez la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc4cc-130">Redémarrez les services.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="dc4cc-131">Une fois que vous avez défini votre topologie, utilisez la procédure suivante pour définir un pool frontal pour votre site.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="dc4cc-132">Pour plus d’informations sur la définition de la topologie, reportez-vous à la rubrique [define and Configure a Topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dc4cc-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="dc4cc-133">Pour définir un pool frontal</span><span class="sxs-lookup"><span data-stu-id="dc4cc-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="dc4cc-134">Dans l’Assistant Définir un nouveau pool frontal, sur la page **Définir le nouveau pool frontal**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="dc4cc-135">Dans la page définir le nom de domaine **complet du pool frontal** , entrez un nom de domaine complet (FQDN) pour le pool que vous créez, cliquez sur **pool de serveurs frontaux Enterprise Edition**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="dc4cc-136">Sur la page **définir les ordinateurs de ce pool** , entrez le nom de domaine complet (FQDN) de l’ordinateur du premier serveur frontal dans le pool, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="dc4cc-137">Répétez cette étape pour tous les ordinateurs supplémentaires (jusqu’à douze) que vous souhaitez ajouter au pool, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="dc4cc-138">Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="dc4cc-139">Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, vous devez activer la case à cocher **Conférence** pour autoriser la messagerie instantanée à plusieurs, mais ne pas sélectionner les cases à cocher Conférence rendez **-** vous, **voix entreprise**ou **contrôle d’admission des appels** , car elles représentent des fonctionnalités de conférence vocale, vidéo et de collaboration.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="dc4cc-140">**Conférence**   cette sélection active un ensemble complet de fonctionnalités, notamment :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="dc4cc-141">la messagerie instantanée avec plus de deux utilisateurs dans le cadre d’une session de messagerie instantanée ;</span><span class="sxs-lookup"><span data-stu-id="dc4cc-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="dc4cc-142">la conférence qui inclut la collaboration sur des documents, le partage d’application et le partage du Bureau ;</span><span class="sxs-lookup"><span data-stu-id="dc4cc-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="dc4cc-143">Conférence a/V, qui permet aux utilisateurs d’effectuer des conférences audio/vidéo (A/V) en temps réel sans avoir besoin de recourir à des services externes, tels que le service Live Meeting ou un pont audio tiers.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="dc4cc-144">**La Conférence**   rendez-vous (PSTN) permet aux utilisateurs de rejoindre la partie audio d’une conférence Lync Server 2013 à l’aide d’un téléphone RTC sans avoir besoin d’un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="dc4cc-145">**Enterprise Voice**   Enterprise Voice est la solution voix sur IP (VoIP) de Lync Server 2013 qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="dc4cc-146">Vous devez déployer cette fonctionnalité si vous envisagez d’utiliser Lync Server 2013 pour les appels vocaux, la messagerie vocale et d’autres fonctions qui utilisent un périphérique matériel ou un client logiciel.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="dc4cc-147">**Le contrôle d’admission des appels (CAC)**   CAC détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel telles que des appels vocaux ou vidéo doivent être établies.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="dc4cc-148">Si vous avez uniquement déployé les fonctionnalités de messagerie instantanée et de présence, CAC n’est pas nécessaire car aucune de ces deux fonctionnalités n’utilise CAC.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="dc4cc-149">\*\*\*\* L’archivage archivage vous permet d’archiver le contenu de messagerie instantanée, le contenu de conférence (réunion), ou les deux, qui sont envoyés via Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="dc4cc-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="dc4cc-150">**Monitoring**   Monitoring Server vous permet de collecter des données numériques qui décrivent la qualité des médias sur votre réseau et les points de terminaison, les informations d’utilisation concernant les appels VoIP, les messages instantanés, les conversations a/V, les réunions, le partage d’application et les transferts de fichiers, ainsi que les informations d’erreur et de dépannage pour les appels ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dc4cc-p109">Si vous souhaitez activer le contrôle d’admission des appels dans votre déploiement, il vous faut activer cette fonctionnalité dans un pool par site central. Le contrôle d’admission des appels est recommandé lorsque vous déployez les fonctionnalités vocales ou la conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="dc4cc-p110">Le tableau suivant indique les fonctionnalités disponibles (en haut) et les fonctions proposées aux utilisateurs (à gauche). Sélectionnez les différents choix dans le tableau pour activer ces fonctionnalités dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="dc4cc-155">Vidéoconférence</span><span class="sxs-lookup"><span data-stu-id="dc4cc-155">Conferencing</span></span></th>
    <th><span data-ttu-id="dc4cc-156">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="dc4cc-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="dc4cc-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="dc4cc-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="dc4cc-158">Contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="dc4cc-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="dc4cc-159">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="dc4cc-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="dc4cc-160">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="dc4cc-161">Vidéoconférence</span><span class="sxs-lookup"><span data-stu-id="dc4cc-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="dc4cc-162">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-162">X</span></span></p></td>
    <td><p><span data-ttu-id="dc4cc-163">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="dc4cc-164">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="dc4cc-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="dc4cc-165">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-165">X</span></span></p></td>
    <td><p><span data-ttu-id="dc4cc-166">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="dc4cc-167">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="dc4cc-168">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="dc4cc-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="dc4cc-169">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-169">X</span></span></p></td>
    <td><p><span data-ttu-id="dc4cc-170">X</span><span class="sxs-lookup"><span data-stu-id="dc4cc-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="dc4cc-171">Sur la page **Sélectionner des rôles serveur colocalisés** , vous pouvez colocaliser le serveur de médiation sur le serveur frontal ou le déployer en tant que serveur autonome.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="dc4cc-172">Vous pouvez colocaliser le serveur de médiation sur le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="dc4cc-173">Si vous avez l’intention d’colocaliser le serveur de médiation sur le pool frontal Enterprise Edition, vérifiez que la case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="dc4cc-174">Les rôles serveur seront déployés sur les serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="dc4cc-175">Si vous avez l’intention de déployer le serveur de médiation en tant que serveur autonome, désactivez la case à cocher appropriée.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="dc4cc-176">Vous allez déployer le serveur de médiation dans une étape de déploiement distincte après avoir déployé entièrement le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dc4cc-177">Nous vous recommandons de colocaliser le serveur de médiation si cela vous est possible.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="dc4cc-178">Pour plus d’informations sur la prise en charge des serveurs de médiation colocalisés ou autonomes, voir <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">composants et topologies pour le serveur de médiation dans Lync server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="dc4cc-179">La page **rôles serveur associés à ce pool frontal** vous permet de définir et d’associer des rôles serveur au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="dc4cc-180">Le rôle suivant est disponible :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-180">The following role is available:</span></span>
    
    <span data-ttu-id="dc4cc-181">**Activer un pool**   Edge définit et associe un serveur Edge unique ou un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="dc4cc-182">Un serveur Edge facilite la communication et la collaboration entre les utilisateurs au sein de l’organisation et les personnes extérieures à l’organisation, y compris les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="dc4cc-183">Vous disposez de deux scénarios pour déployer et associer des rôles serveur :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="dc4cc-p116">Dans le premier scénario, vous définissez une nouvelle topologie pour un nouvelle installation. Vous pouvez procéder à l’installation de deux façons différentes :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="dc4cc-186">Laissez la case à cocher désactivée et définissez la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="dc4cc-187">Une fois que vous avez publié, configuré et testé les rôles serveur frontal et principal, vous pouvez réexécuter le générateur de topologie pour ajouter les serveurs de rôle à la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="dc4cc-188">Cette stratégie vous permettra de tester le pool frontal et le serveur exécutant SQL Server sans complications supplémentaires de rôles supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="dc4cc-189">Une fois que vous avez terminé les tests initiaux, vous pouvez réexécuter le générateur de topologie pour sélectionner les rôles à déployer.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="dc4cc-190">Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="dc4cc-191">Pour le scénario 2, vous disposez d’un déploiement existant et votre infrastructure est prête pour de nouveaux rôles, ou vous devez associer des rôles existants à un nouveau serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="dc4cc-192">Dans ce cas, vous allez sélectionner les rôles que vous envisagez de déployer ou d’associer au nouveau serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="dc4cc-193">Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="dc4cc-194">Dans la page **Définir le magasin SQL**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="dc4cc-195">Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="dc4cc-196">Pour définir une nouvelle instance SQL Server pour stocker les informations du pool, cliquez sur **nouveau** , puis spécifiez le **nom de domaine complet SQL Server**dans la boîte de dialogue **définir un nouveau magasin SQL** .</span><span class="sxs-lookup"><span data-stu-id="dc4cc-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="dc4cc-197">Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée**, puis spécifiez le nom de l’instance.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="dc4cc-198">Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="dc4cc-199">Pour utiliser la mise en miroir SQL, sélectionnez **Activer la mise en miroir SQL** et sélectionnez une instance existante ou créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="dc4cc-200">Dans la page **Définir le partage de fichiers**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="dc4cc-201">Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="dc4cc-202">Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers**. Dans la zone **Nom de domaine complet du serveur de fichiers**, entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="dc4cc-203">Le partage de fichiers pour Lync Server 2013 ne peut pas se trouver sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="dc4cc-204">Notez que dans cet exemple, le partage de fichiers se situait sur le serveur principal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="dc4cc-205">Il ne s’agit peut-être pas d’un emplacement optimal pour les besoins de votre organisation ; un serveur de fichiers peut s’avérer être un meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="dc4cc-206">Vous pouvez définir le partage de fichiers sans qu’il soit nécessaire de le créer.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="dc4cc-207">Vous devrez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="dc4cc-208">Dans la page **Spécifier l’URL des services web**, effectuez l’une ou plusieurs des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="dc4cc-209">L’URL de base correspond à l’identité des services web pour l’URL, moins https://.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="dc4cc-210">Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="dc4cc-211">Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="dc4cc-212">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="dc4cc-213">Si vous configurez l’équilibrage de charge DNS, activez la case à cocher **remplacer le nom de domaine complet du pool des services Web internes** , entrez l’URL de base interne (qui doit être différente du nom de\<domaine complet du\>pool et peut être, par exemple, l’URL de base interne) dans **URL de base interne**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="dc4cc-214">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="dc4cc-215"><STRONG>Utilisez uniquement des caractères standard</STRONG> (tels que a – z, a – z, 0 – 9 et des traits d’Union) lors de la définition des URL ou des noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="dc4cc-216">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="dc4cc-217">Les caractères non standard d’une URL ou d’un nom de domaine complet ne sont souvent pas pris en charge par le DNS externe et les autorités de certification publiques (c’est-à-dire, lorsque l’URL ou le nom de domaine complet doivent être attribués au nom de sujet ou à l’autre nom de l’objet dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="dc4cc-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="dc4cc-218">Entrez l’URL de base externe dans **URL de base externe** (facultatif).</span><span class="sxs-lookup"><span data-stu-id="dc4cc-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="dc4cc-219">Entrez l’URL de base externe pour la différencier de votre nom de domaine interne.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="dc4cc-220">Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="dc4cc-221">Définissez alors l’URL à l’aide du nom de domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="dc4cc-222">Ceci est également important dans le cas d’un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="dc4cc-223">Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="dc4cc-224">La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dc4cc-225">Pour utiliser l’équilibrage de charge DNS, vous devez créer les enregistrements DNS appropriés.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="dc4cc-226">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurer DNS pour l’équilibrage de charge dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="dc4cc-227">Si vous avez sélectionné **Conférence** dans la page **Sélectionner des fonctionnalités** , dans la page **Sélectionner un serveur Office Web Apps Server** , sélectionnez **associer un pool à un serveur Office Web Apps Server** , puis cliquez sur **nouveau** (ou sélectionnez un serveur Office Web Apps existant dans la liste déroulante).</span><span class="sxs-lookup"><span data-stu-id="dc4cc-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="dc4cc-228">Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="dc4cc-229">Si Office Web Apps Server est installé sur site et dans la même zone de réseau que Lync Server 2013, l’option le **serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** ne doit pas être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="dc4cc-230">Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dc4cc-231">Pour plus d’informations, reportez-vous à la rubrique Configuration de l' <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">intégration avec Office Web Apps Server et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="dc4cc-232">Dans la page **Définir le magasin SQL Server d’archivage**, sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="dc4cc-233">Dans la page **Définir le magasin SQL Server pour la surveillance**, sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="dc4cc-234">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-234">Click **Next**.</span></span> <span data-ttu-id="dc4cc-235">Si vous avez défini d’autres serveurs de rôle sur la page **rôles serveur associés avec ce pool frontal** , des pages d’Assistant Configuration de rôle distinctes s’ouvrent pour vous permettre de configurer les rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="dc4cc-236">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="dc4cc-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="dc4cc-237">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc4cc-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="dc4cc-238">Si vous n’avez pas sélectionné de rôles serveur supplémentaires à configurer et à déployer, ou si vous avez terminé la configuration de rôles serveur supplémentaires, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="dc4cc-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

