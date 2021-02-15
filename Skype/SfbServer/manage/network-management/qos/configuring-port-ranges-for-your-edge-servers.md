---
title: Configuration des plages de ports et d’une qualité de service pour vos serveurs Edge
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article explique comment configurer des plages de ports pour les serveurs Edge et comment configurer une stratégie de qualité de service pour vos serveurs Edge A/V.
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832904"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="cecba-103">Configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs Edge dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cecba-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="cecba-104">Cet article explique comment configurer des plages de ports pour les serveurs Edge et comment configurer une stratégie de qualité de service pour vos serveurs Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="cecba-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="cecba-105">Configurer des plages de ports</span><span class="sxs-lookup"><span data-stu-id="cecba-105">Configure port ranges</span></span>

<span data-ttu-id="cecba-106">Avec les serveurs Edge, vous n’avez pas besoin de configurer des plages de ports distinctes pour l’audio, la vidéo et le partage d’applications . De même, les plages de ports utilisées pour les serveurs Edge n’ont pas besoin de correspondre aux plages de ports utilisées avec vos serveurs de conférence, d’application et de médiation.</span><span class="sxs-lookup"><span data-stu-id="cecba-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="cecba-107">Avant de poursuivre notre exemple, il est important de souligner que même si cette option existe, nous vous recommandons de ne pas modifier les plages de ports, car cela peut nuire à certains scénarios si vous vous déplacez hors de la plage de ports 50000.</span><span class="sxs-lookup"><span data-stu-id="cecba-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="cecba-108">Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’applications et de médiation afin d’utiliser ces plages de ports :</span><span class="sxs-lookup"><span data-stu-id="cecba-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cecba-109">Type de paquet</span><span class="sxs-lookup"><span data-stu-id="cecba-109">Packet Type</span></span></th>
<th><span data-ttu-id="cecba-110">Port de début</span><span class="sxs-lookup"><span data-stu-id="cecba-110">Starting Port</span></span></th>
<th><span data-ttu-id="cecba-111">Nombre de ports réservés</span><span class="sxs-lookup"><span data-stu-id="cecba-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cecba-112">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="cecba-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="cecba-113">40803</span><span class="sxs-lookup"><span data-stu-id="cecba-113">40803</span></span></p></td>
<td><p><span data-ttu-id="cecba-114">8348</span><span class="sxs-lookup"><span data-stu-id="cecba-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cecba-115">Audio</span><span class="sxs-lookup"><span data-stu-id="cecba-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="cecba-116">49152</span><span class="sxs-lookup"><span data-stu-id="cecba-116">49152</span></span></p></td>
<td><p><span data-ttu-id="cecba-117">8348</span><span class="sxs-lookup"><span data-stu-id="cecba-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cecba-118">Vidéo</span><span class="sxs-lookup"><span data-stu-id="cecba-118">Video</span></span></p></td>
<td><p><span data-ttu-id="cecba-119">57500</span><span class="sxs-lookup"><span data-stu-id="cecba-119">57500</span></span></p></td>
<td><p><span data-ttu-id="cecba-120">8034</span><span class="sxs-lookup"><span data-stu-id="cecba-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cecba-121"><strong>Totaux</strong></span><span class="sxs-lookup"><span data-stu-id="cecba-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="cecba-122">24730</span><span class="sxs-lookup"><span data-stu-id="cecba-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cecba-123">Comme vous pouvez le constater, vos plages de ports pour l’audio, la vidéo et le partage d’application commencent au port 40803 et englobent un total de 24 732 ports.</span><span class="sxs-lookup"><span data-stu-id="cecba-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="cecba-124">Si vous préférez, vous pouvez configurer un serveur Edge donné pour utiliser ces valeurs de port globales en exécutant une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="cecba-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="cecba-125">Ou utilisez la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="cecba-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="cecba-126">Vous pouvez vérifier les paramètres de port actuels de vos serveurs Edge à l’aide de cette commande Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="cecba-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="cecba-127">Là encore, bien que nous fournissions ces options, nous vous recommandons vivement de laisser les éléments tels qu’ils sont pour la configuration du port.</span><span class="sxs-lookup"><span data-stu-id="cecba-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="cecba-128">Configurer une stratégie QoS pour vos serveurs Edge A/V</span><span class="sxs-lookup"><span data-stu-id="cecba-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="cecba-129">En plus de créer des stratégies de QoS pour vos serveurs de conférence, d’application et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="cecba-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="cecba-130">Toutefois, les stratégies utilisées sur vos serveurs Edge sont différentes des stratégies utilisées sur vos serveurs de conférence, d’application et de médiation.</span><span class="sxs-lookup"><span data-stu-id="cecba-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="cecba-131">Pour les serveurs de conférence, d’application et de médiation, vous avez spécifié une plage de ports source ; avec les serveurs Edge, vous devez spécifier une plage de ports de destination.</span><span class="sxs-lookup"><span data-stu-id="cecba-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="cecba-132">Pour cette raison, vous ne pouvez pas simplement appliquer les stratégies de qualité de service de conférence, d’application et de serveur de médiation à vos serveurs Edge : ces stratégies ne fonctionneront simplement pas.</span><span class="sxs-lookup"><span data-stu-id="cecba-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="cecba-133">Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer ces stratégies à vos serveurs Edge uniquement.</span><span class="sxs-lookup"><span data-stu-id="cecba-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="cecba-134">La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisés pour gérer la qualité de service sur les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="cecba-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="cecba-135">Bien entendu, il est possible que vos serveurs Edge soient des serveurs autonomes qui n’ont pas de compte Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cecba-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="cecba-136">Si c’est le cas, vous pouvez utiliser la stratégie de groupe locale au lieu de la stratégie de groupe Active Directory : la seule différence est que vous devez créer ces stratégies locales à l’aide de l’Éditeur de stratégie de groupe local et créer individuellement le même ensemble de stratégies sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cecba-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="cecba-137">Pour démarrer l’Éditeur de stratégie de groupe locale sur un serveur Edge, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="cecba-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="cecba-138">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cecba-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="cecba-139">Dans la **boîte de** dialogue Exécuter, **tapez gpedit.msc,** puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="cecba-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="cecba-140">Si vous créez des stratégies basées sur Active Directory, vous devez vous connecter à un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="cecba-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="cecba-141">Dans ce cas, ouvrez la gestion des stratégies de groupe (cliquez sur **Démarrer,** pointez sur Outils d’administration, puis cliquez sur Gestion des stratégies de **groupe),** puis complétez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cecba-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="cecba-142">Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="cecba-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="cecba-143">Par exemple, si tous vos ordinateurs Skype Entreprise Server se trouvent dans une ou plusieurs de vos ordinateurs nommés Skype Entreprise Server, la nouvelle stratégie doit être créée dans l’ou Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cecba-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="cecba-144">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un GPO dans ce domaine, puis le **lier ici.**</span><span class="sxs-lookup"><span data-stu-id="cecba-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="cecba-145">Dans la **boîte** de dialogue Nouvel objet de stratégie de  groupe, tapez un nom pour le nouvel objet de stratégie de groupe dans la zone Nom (par exemple, Skype Entreprise **Server Audio),** puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cecba-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="cecba-146">Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="cecba-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="cecba-147">À partir de là, le processus est identique, que vous créiez une stratégie Active Directory ou une stratégie locale :</span><span class="sxs-lookup"><span data-stu-id="cecba-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="cecba-148">Dans l’Éditeur de gestion des stratégies de groupe ou l’Éditeur de stratégie de groupe local, développez **Configuration** ordinateur, Développez Stratégies, Développez **Paramètres Windows,** cliquez avec le bouton droit sur **QoS** basé sur la stratégie, puis cliquez sur Créer une **stratégie.**</span><span class="sxs-lookup"><span data-stu-id="cecba-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="cecba-149">Dans la boîte de dialogue **QoS** basée sur la stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, Skype Entreprise **Server Audio)** dans la zone **Nom.**</span><span class="sxs-lookup"><span data-stu-id="cecba-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="cecba-150">Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**.</span><span class="sxs-lookup"><span data-stu-id="cecba-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="cecba-151">Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cecba-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="cecba-152">Sur la page suivante, assurez-vous que toutes les **applications** sont sélectionnées, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cecba-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="cecba-153">Ce paramètre indique au réseau de rechercher tous les paquets avec un marquage DSCP de 46, et pas seulement les paquets créés par une application spécifique.</span><span class="sxs-lookup"><span data-stu-id="cecba-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="cecba-154">Sur la troisième page, assurez-vous que les adresses **IP source Et** Toute adresse IP de **destination** sont sélectionnées, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cecba-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="cecba-155">Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.</span><span class="sxs-lookup"><span data-stu-id="cecba-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="cecba-156">Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**.</span><span class="sxs-lookup"><span data-stu-id="cecba-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="cecba-157">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Skype Entreprise Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="cecba-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="cecba-158">Sous le titre **Spécifiez le numéro de port de destination,** **sélectionnez À partir de ce port ou plage de destination.**</span><span class="sxs-lookup"><span data-stu-id="cecba-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="cecba-159">Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="cecba-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="cecba-160">Par exemple, si vous avez réservé les ports 49152 à 57500 pour le trafic audio, entrez la plage de ports en utilisant ce format : **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="cecba-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="cecba-161">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="cecba-161">Click **Finish**.</span></span>

<span data-ttu-id="cecba-162">Après avoir créé la stratégie QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="cecba-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="cecba-163">Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="cecba-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="cecba-164">Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server Video).**</span><span class="sxs-lookup"><span data-stu-id="cecba-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="cecba-p113">Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).</span><span class="sxs-lookup"><span data-stu-id="cecba-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="cecba-168">Utilisez la plage de ports précédemment configurée pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="cecba-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="cecba-169">Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports sur celle-ci : **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="cecba-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="cecba-170">Là encore, il doit être configuré comme plage de ports de destination.</span><span class="sxs-lookup"><span data-stu-id="cecba-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="cecba-171">Si vous décidez de créer une stratégie pour la gestion du trafic de partage d’application, vous devez créer une troisième stratégie, en faisant les substitutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cecba-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="cecba-172">Utilisez un nom de stratégie différent (et unique) (par exemple, partage d’application Skype Entreprise **Server).**</span><span class="sxs-lookup"><span data-stu-id="cecba-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="cecba-p115">Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).</span><span class="sxs-lookup"><span data-stu-id="cecba-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="cecba-176">Utilisez la plage de ports précédemment configurée pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="cecba-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="cecba-177">Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="cecba-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="cecba-178">Les nouvelles stratégies que vous avez créées ne prennent effet qu’une fois la stratégie de groupe actualisée sur vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="cecba-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="cecba-179">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :</span><span class="sxs-lookup"><span data-stu-id="cecba-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="cecba-180">Cette commande peut être exécuté à partir de Skype Entreprise Server ou à partir de n’importe quelle fenêtre de commande qui s’exécute sous les informations d’identification de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="cecba-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="cecba-181">Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="cecba-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="cecba-182">Notez que vous devrez peut-être redémarrer le serveur Edge même après avoir Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="cecba-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="cecba-183">Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cecba-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="cecba-184">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cecba-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="cecba-185">Dans la **boîte de** dialogue Exécuter, tapez **regedit,** puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="cecba-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="cecba-186">Dans l’Éditeur du Registre, développez **HKEY \_ LOCAL \_ MACHINE,** développez **SYSTEM,** **CurrentControlSet,** développez **les services,** puis **développez Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="cecba-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="cecba-187">Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**.</span><span class="sxs-lookup"><span data-stu-id="cecba-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="cecba-188">Une fois la nouvelle clé de Registre créée, tapez **QoS,** puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="cecba-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="cecba-189">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**.</span><span class="sxs-lookup"><span data-stu-id="cecba-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="cecba-190">Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA,** puis appuyez sur Entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="cecba-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="cecba-191">Double-cliquez sur **Ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="cecba-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="cecba-192">Dans la boîte **de dialogue Modifier**  la chaîne, tapez **1** dans la zone de données Valeur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cecba-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="cecba-193">Fermez l’Éditeur du Registre et redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cecba-193">Close the Registry Editor and reboot your computer.</span></span>
