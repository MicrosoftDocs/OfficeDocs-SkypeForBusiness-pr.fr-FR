---
title: 'Lync Server 2013 : configuration d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation'
description: 'Lync Server 2013 : configuration d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ee82c5f1f6b3025c4052b7e27c1013e0624b756
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545640"
---
# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="4b5c3-103">Configuration d’une stratégie de qualité de service dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation</span><span class="sxs-lookup"><span data-stu-id="4b5c3-103">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b5c3-104">_**Dernière modification de la rubrique :** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="4b5c3-104">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="4b5c3-p101">La configuration de plages de ports facilite l’utilisation de la qualité de service en s’assurant que tout le trafic d’un type donné (par exemple, tout le trafic audio) passe par le même ensemble de ports. Cela permet au système d’identifier et de marquer facilement un paquet donné : si le port 49152 est réservé au trafic audio, les paquets qui passent par le port 49152 peuvent être marqués avec un code DSCP qui indique qu’il s’agit d’un paquet audio. Cela permet aux routeurs d’identifier le paquet comme étant un paquet audio, et de lui donner une priorité supérieure aux paquets non marqués (par exemple les paquets utilisés pour copier un fichier d’un serveur sur un autre).</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="4b5c3-108">Cependant, la limitation d’un ensemble de ports à un type de trafic spécifique ne permet pas que ces paquets soient automatiquement marqués avec le code DSCP approprié.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-108">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="4b5c3-109">En plus de la définition des plages de ports, vous devez également créer des stratégies de qualité de service qui spécifient le code DSCP à associer à chaque plage de ports.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-109">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="4b5c3-110">Pour Microsoft Lync Server 2013, cela signifie généralement la création de deux stratégies : une pour l’audio et une pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-110">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="4b5c3-111">Il est facile de créer et de gérer des stratégies de qualité de service avec la Stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-111">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="4b5c3-112">(Ces stratégies peuvent également être créées à l’aide de stratégies de sécurité locales.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-112">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="4b5c3-113">Toutefois, vous devez répéter la même procédure sur chaque ordinateur.) Votre ensemble initial de stratégies QoS (une pour l’audio et une pour la vidéo) doit être appliqué uniquement aux ordinateurs Lync Server exécutant le serveur de conférence, le serveur d’applications et/ou les services de serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-113">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="4b5c3-114">Si tous ces ordinateurs sont situés dans la même unité d’organisation Active Directory, il vous suffit d’assigner le nouvel objet de stratégie de groupe (GPO) à cette unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-114">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="4b5c3-115">Vous pouvez également procéder d’une autre façon pour cibler les ordinateurs spécifiés avec cette stratégie ; par exemple, vous pouvez placer les ordinateurs dans un groupe de sécurité, puis utiliser le filtrage de sécurité de la stratégie de groupe pour appliquer l’objet de stratégie de groupe uniquement à ce groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-115">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="4b5c3-116">Afin de créer une stratégie de qualité de service pour gérer l’audio, connectez-vous à un ordinateur sur lequel la gestion des stratégies de groupe est installée.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-116">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="4b5c3-117">Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **gestion des stratégies de groupe**), puis effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="4b5c3-117">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="4b5c3-118">Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-118">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="4b5c3-119">Par exemple, si tous vos ordinateurs Lync Server se trouvent dans une unité d’organisation nommée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-119">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="4b5c3-120">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-120">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="4b5c3-121">Dans la boîte de dialogue **nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, service **QoS Lync Server**), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-121">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="4b5c3-122">Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-122">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="4b5c3-123">Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **Stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur la stratégie**, puis cliquez sur **Créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-123">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="4b5c3-124">Dans la boîte de dialogue **QoS basée** sur la stratégie, dans la page d’accueil, tapez un nom pour la nouvelle stratégie (par exemple, **Lync Server QoS**) dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="4b5c3-124">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="4b5c3-125">Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-125">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="4b5c3-126">Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-126">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="4b5c3-p107">Dans la page suivante, assurez-vous que **Toutes les applications** est sélectionné, puis cliquez sur **Suivant**. Cela permet de s’assurer que toutes les applications feront correspondre les paquets de la plage de ports spécifiée au code DSCP correct.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="4b5c3-p108">Dans la troisième page, vérifiez que **Toute adresse IP source et Toute adresse IP de destination** sont sélectionnés, puis cliquez sur **Suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="4b5c3-131">Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="4b5c3-132">Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="4b5c3-p110">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservez les ports 49152 à 57500 pour le trafic audio, tapez la plage de ports au format : **49152:57500**. Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b5c3-p111">La valeur DSCP 46 est arbitraire : bien que DSCP 46 soit souvent utilisé pour marquer les paquets audio, vous n’êtes pas obligé d’utiliser cette valeur pour les communications audio. Si vous avez déjà mis en œuvre QoS et utilisez un autre code DSCP pour l’audio (par exemple, DSCP 40), configurez votre stratégie de qualité de service pour qu’elle utilise ce code (c’est-à-dire, 40 pour l’audio). Si vous implémentez la qualité de service, alors il est recommandé d’utiliser DSCP 46 pour l’audio, car cette valeur est utilisée en général pour marquer les paquets audio.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="4b5c3-p112">Une fois la stratégie QoS créée pour le trafic audio, créez une seconde stratégie pour le trafic vidéo (et une troisième pour la gestion du trafic de partage d’applications, si vous le souhaitez). Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="4b5c3-142">Utilisez un nom de stratégie différent et unique (par exemple, **Vidéo Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="4b5c3-142">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="4b5c3-p113">Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="4b5c3-p114">Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme ceci : **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="4b5c3-148">Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4b5c3-148">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="4b5c3-149">Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="4b5c3-149">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="4b5c3-p115">Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="4b5c3-p116">Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="4b5c3-155">Les nouvelles stratégies que vous avez créées ne prendront effet qu’après l’actualisation de la stratégie de groupe sur vos ordinateurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-155">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="4b5c3-156">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :</span><span class="sxs-lookup"><span data-stu-id="4b5c3-156">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="4b5c3-157">Cette commande peut être exécutée à partir de Lync Server Management Shell ou à partir de n’importe quelle fenêtre de commande exécutée sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-157">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="4b5c3-158">Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-158">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="4b5c3-159">Pour vérifier que les nouvelles stratégies QoS ont été appliquées, procédez ainsi :</span><span class="sxs-lookup"><span data-stu-id="4b5c3-159">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="4b5c3-160">Sur l’ordinateur Lync Server, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-160">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="4b5c3-161">Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-161">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="4b5c3-162">Dans l’éditeur du Registre, développez **ordinateur**, **HKEY \_ local \_ machine**, **logiciel**, développez **stratégies**, **Microsoft**, **Windows**, puis cliquez sur **QoS**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-162">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="4b5c3-163">Sous **QoS** des clés de registre pour chaque stratégie QoS créée doivent s’afficher.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-163">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="4b5c3-164">Par exemple, si vous avez créé deux nouvelles stratégies (l’une nommée QoS audio Lync Server et l’autre nommée QoS vidéo de Lync Server), vous devez les entrées de Registre pour la qualité de service (QoS) audio Lync Server et la qualité de service (QoS) vidéo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-164">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="4b5c3-165">Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b5c3-165">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="4b5c3-166">Pour ce faire, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-166">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="4b5c3-167">Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-167">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="4b5c3-168">Dans l’éditeur du Registre, développez **HKEY \_ local \_ machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-168">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="4b5c3-p120">Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="4b5c3-p121">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="4b5c3-173">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-173">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="4b5c3-174">Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-174">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="4b5c3-175">Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-175">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

