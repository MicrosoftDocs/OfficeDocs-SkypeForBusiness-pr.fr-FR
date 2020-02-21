---
title: Configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30fece45c4b13bd9cd2c9243dd21cdac1d779733
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="7aae8-102">Configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aae8-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aae8-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7aae8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7aae8-104">En plus de créer des stratégies de qualité de service pour vos serveurs de conférence, d’application et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="7aae8-104">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="7aae8-105">Toutefois, les stratégies utilisées sur vos serveurs Edge sont différentes des stratégies utilisées sur vos serveurs de conférence, d’application et de médiation.</span><span class="sxs-lookup"><span data-stu-id="7aae8-105">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="7aae8-106">Pour les serveurs de conférence, d’application et de médiation, vous avez spécifié une plage de ports sources ; avec des serveurs Edge, vous devez spécifier une plage de ports de destination.</span><span class="sxs-lookup"><span data-stu-id="7aae8-106">For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="7aae8-107">Pour cette raison, vous ne pouvez pas simplement appliquer les stratégies QoS serveur de conférence, d’application et de médiation à vos serveurs Edge : ces stratégies ne fonctionneront tout simplement pas.</span><span class="sxs-lookup"><span data-stu-id="7aae8-107">Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="7aae8-108">Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer ces stratégies à vos serveurs Edge uniquement.</span><span class="sxs-lookup"><span data-stu-id="7aae8-108">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="7aae8-109">La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisés pour gérer la qualité de service sur les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="7aae8-109">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="7aae8-110">Bien entendu, il est possible que vos serveurs Edge soient des serveurs autonomes qui n’ont pas de comptes Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7aae8-110">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="7aae8-111">Si c’est le cas, vous pouvez utiliser la stratégie de groupe locale au lieu de la stratégie de groupe Active Directory : la seule différence réside dans le fait que vous devez créer ces stratégies locales à l’aide de l’éditeur de stratégie de groupe local et créer un même ensemble de stratégies sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7aae8-111">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="7aae8-112">Pour démarrer l’éditeur de stratégie de groupe local sur un serveur Edge, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7aae8-112">To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="7aae8-113">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="7aae8-114">Dans la boîte de dialogue **exécuter** , tapez **gpedit. msc** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="7aae8-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="7aae8-115">Si vous créez des stratégies basées sur Active Directory, vous devez ouvrir une session sur un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="7aae8-115">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="7aae8-116">Dans ce cas, ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **gestion des stratégies de groupe**), puis effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7aae8-116">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="7aae8-117">Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="7aae8-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="7aae8-118">Par exemple, si tous vos ordinateurs Lync Server se trouvent dans une unité d’organisation nommée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7aae8-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="7aae8-119">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="7aae8-120">Dans la boîte de dialogue **Nouvel objet GPO**, tapez le nom du nouvel objet de stratégie de groupe dans la zone **Nom** (par exemple, **Audio Lync Server**), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="7aae8-121">Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="7aae8-122">À partir de là, le processus est identique, qu’il s’agisse de la création d’une stratégie Active Directory ou d’une stratégie locale :</span><span class="sxs-lookup"><span data-stu-id="7aae8-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="7aae8-123">Dans l’éditeur de gestion des stratégies de groupe ou l’éditeur de stratégie de groupe local, développez **Configuration ordinateur**, **stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée**sur la stratégie, puis cliquez sur **créer une stratégie**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="7aae8-p105">Dans la boîte de dialogue **QoS basée sur la stratégie**, dans la page d’accueil, tapez le nom de la nouvelle stratégie (par exemple, **Audio Lync Server**) dans la zone **Nom**. Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="7aae8-127">Dans la page suivante, assurez-vous que **Toutes les applications** est sélectionné, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-127">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="7aae8-128">Ce paramètre indique au réseau de rechercher tous les paquets dont le marquage DSCP est de 46, pas seulement les paquets créés par une application spécifique.</span><span class="sxs-lookup"><span data-stu-id="7aae8-128">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="7aae8-129">Sur la troisième page, assurez-vous que **toutes les adresses IP source** et **toute adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-129">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="7aae8-130">Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.</span><span class="sxs-lookup"><span data-stu-id="7aae8-130">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="7aae8-131">Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="7aae8-132">Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="7aae8-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="7aae8-133">Sous le titre **Spécifiez le numéro de port de destination**, sélectionnez **à partir de ce port ou cette plage de destination**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-133">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="7aae8-134">Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="7aae8-134">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="7aae8-135">Par exemple, si vous avez réservé les ports 49152 via les ports 57500 pour le trafic audio, entrez ensuite la plage de ports au format suivant : **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-135">For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="7aae8-136">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-136">Click **Finish**.</span></span>

<span data-ttu-id="7aae8-137">Une fois que vous avez créé la stratégie de QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="7aae8-137">After you have created the QoS policy for audio traffic you should create a second policy for video traffic.</span></span> <span data-ttu-id="7aae8-138">Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7aae8-138">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="7aae8-139">Utilisez un nom de stratégie différent et unique (par exemple, **Vidéo Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="7aae8-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="7aae8-p111">Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).</span><span class="sxs-lookup"><span data-stu-id="7aae8-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="7aae8-143">Utilisez la plage de ports configurée précédemment pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="7aae8-143">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="7aae8-144">Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme ceci : **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-144">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="7aae8-145">Une fois encore, la plage de ports de destination doit être configurée.</span><span class="sxs-lookup"><span data-stu-id="7aae8-145">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="7aae8-146">Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7aae8-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="7aae8-147">Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="7aae8-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="7aae8-p113">Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).</span><span class="sxs-lookup"><span data-stu-id="7aae8-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="7aae8-p114">Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="7aae8-153">Les nouvelles stratégies que vous avez créées ne prendront effet qu’après l’actualisation de la stratégie de groupe sur vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="7aae8-153">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="7aae8-154">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :</span><span class="sxs-lookup"><span data-stu-id="7aae8-154">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="7aae8-155">Cette commande peut être exécutée à partir de Lync Server ou de n’importe quelle fenêtre de commande exécutée sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7aae8-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="7aae8-156">Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="7aae8-157">Notez que vous devrez peut-être redémarrer le serveur Edge même après avoir exécuté gpudate. exe.</span><span class="sxs-lookup"><span data-stu-id="7aae8-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="7aae8-158">Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7aae8-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="7aae8-159">Pour ce faire, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="7aae8-160">Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="7aae8-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="7aae8-161">Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="7aae8-p117">Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="7aae8-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="7aae8-p118">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="7aae8-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="7aae8-p119">Double-cliquez sur **Ne pas utiliser NLA**. Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7aae8-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="7aae8-168">Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7aae8-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

