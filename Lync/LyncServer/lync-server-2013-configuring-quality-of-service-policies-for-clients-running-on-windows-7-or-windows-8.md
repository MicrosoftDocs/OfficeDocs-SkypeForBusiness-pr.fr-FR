---
title: 'Lync Server 2013: configuration des stratégies de qualité de service pour les clients exécutant Windows 7 ou Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b36c16056ef378910dc0cd5c885dc7b5d896d860
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="66e03-102">Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients exécutant Windows 7 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="66e03-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e03-103">_**Dernière modification de la rubrique:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="66e03-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="66e03-104">Outre la spécification des plages de port destinées aux clients Lync, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="66e03-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="66e03-105">(La qualité de service créée pour les serveurs de conférence, d’application et de médiation ne doit pas être appliquée aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Lync 2013 et Windows 7 ou Windows 8.</span><span class="sxs-lookup"><span data-stu-id="66e03-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="66e03-106">L’exemple suivant utilise ce jeu de plages de ports pour créer une stratégie audio et une stratégie de vidéo:</span><span class="sxs-lookup"><span data-stu-id="66e03-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66e03-107">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="66e03-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="66e03-108">Début du port</span><span class="sxs-lookup"><span data-stu-id="66e03-108">Port Start</span></span></th>
<th><span data-ttu-id="66e03-109">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="66e03-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66e03-110">Audio</span><span class="sxs-lookup"><span data-stu-id="66e03-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="66e03-111">50020</span><span class="sxs-lookup"><span data-stu-id="66e03-111">50020</span></span></p></td>
<td><p><span data-ttu-id="66e03-112">CX3-20</span><span class="sxs-lookup"><span data-stu-id="66e03-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e03-113">Vidéo</span><span class="sxs-lookup"><span data-stu-id="66e03-113">Video</span></span></p></td>
<td><p><span data-ttu-id="66e03-114">58000</span><span class="sxs-lookup"><span data-stu-id="66e03-114">58000</span></span></p></td>
<td><p><span data-ttu-id="66e03-115">CX3-20</span><span class="sxs-lookup"><span data-stu-id="66e03-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e03-116">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="66e03-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="66e03-117">42000</span><span class="sxs-lookup"><span data-stu-id="66e03-117">42000</span></span></p></td>
<td><p><span data-ttu-id="66e03-118">CX3-20</span><span class="sxs-lookup"><span data-stu-id="66e03-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e03-119">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="66e03-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="66e03-120">42020</span><span class="sxs-lookup"><span data-stu-id="66e03-120">42020</span></span></p></td>
<td><p><span data-ttu-id="66e03-121">CX3-20</span><span class="sxs-lookup"><span data-stu-id="66e03-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66e03-122">Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 7 ou Windows 8, vous devez d’abord vous connecter à un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="66e03-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="66e03-123">Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="66e03-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="66e03-124">Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="66e03-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="66e03-125">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.</span><span class="sxs-lookup"><span data-stu-id="66e03-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="66e03-126">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et associez-le ici**.</span><span class="sxs-lookup"><span data-stu-id="66e03-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="66e03-127">Dans la boîte de dialogue **nouvel objet GPO** , tapez le nom du nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **audio Lync**), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66e03-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="66e03-128">Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="66e03-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="66e03-129">Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **stratégies**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="66e03-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="66e03-130">Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **audio Lync**) dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="66e03-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="66e03-131">Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**.</span><span class="sxs-lookup"><span data-stu-id="66e03-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="66e03-132">Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="66e03-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="66e03-133">Dans la page suivante, assurez-vous que l’option **toutes les applications** est sélectionnée, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="66e03-133">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="66e03-134">Ce paramètre indique au réseau de chercher tous les paquets avec un marquage DSCP de 46, pas seulement les paquets créés par une application spécifique.</span><span class="sxs-lookup"><span data-stu-id="66e03-134">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="66e03-135">Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="66e03-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="66e03-136">Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.</span><span class="sxs-lookup"><span data-stu-id="66e03-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="66e03-137">Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** .</span><span class="sxs-lookup"><span data-stu-id="66e03-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="66e03-138">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Lync Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="66e03-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="66e03-139">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**.</span><span class="sxs-lookup"><span data-stu-id="66e03-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="66e03-140">Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="66e03-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="66e03-141">Par exemple, si vous avez réservé ports 50020 via ports 50039 pour le trafic audio, entrez la plage de ports à l’aide du format suivant: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="66e03-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="66e03-142">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="66e03-142">Click **Finish**.</span></span>

<span data-ttu-id="66e03-143">Une fois que vous avez créé la stratégie QoS pour le son, vous devez créer une deuxième stratégie pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="66e03-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="66e03-144">Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes:</span><span class="sxs-lookup"><span data-stu-id="66e03-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="66e03-145">Utilisez un nom de stratégie différent (et unique) (par exemple, **vidéo Lync**).</span><span class="sxs-lookup"><span data-stu-id="66e03-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="66e03-146">Définissez la valeur DSCP sur **34** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="66e03-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="66e03-147">(Comme indiqué précédemment, vous n’avez pas besoin d’utiliser la valeur DSCP 34; il vous suffit d’affecter une valeur DSCP différente de celle utilisée pour l’audio.)</span><span class="sxs-lookup"><span data-stu-id="66e03-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="66e03-148">Utilisez la plage de ports déjà configurée pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="66e03-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="66e03-149">Par exemple, si vous avez réservé ports 58000 à 58019 pour la vidéo, définissez la plage de ports comme suit: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="66e03-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="66e03-150">Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="66e03-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="66e03-151">Utilisez un nom de stratégie différent (et unique) (par exemple, le **partage d’applications serveur Lync**).</span><span class="sxs-lookup"><span data-stu-id="66e03-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="66e03-152">Définissez la valeur DSCP sur **24** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="66e03-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="66e03-153">(De nouveau, cette valeur ne doit pas être de 24; il doit simplement être différent des valeurs DSCP utilisées pour l’audio et la vidéo.)</span><span class="sxs-lookup"><span data-stu-id="66e03-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="66e03-154">Utilisez la plage de ports déjà configurée pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="66e03-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="66e03-155">Par exemple, si vous avez réservé ports 42000 à 42019 pour le partage d’application, définissez l’intervalle de ports comme suit: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="66e03-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="66e03-156">Pour une stratégie de transfert de fichiers:</span><span class="sxs-lookup"><span data-stu-id="66e03-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="66e03-157">Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="66e03-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="66e03-158">Définissez la valeur DSCP sur **14**.</span><span class="sxs-lookup"><span data-stu-id="66e03-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="66e03-159">(De nouveau, cette valeur ne doit pas être 14; il doit simplement s’agir d’un code DSCP unique.)</span><span class="sxs-lookup"><span data-stu-id="66e03-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="66e03-160">Utilisez la plage de ports déjà configurée pour l’application.</span><span class="sxs-lookup"><span data-stu-id="66e03-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="66e03-161">Par exemple, si vous avez réservé ports 42020 à 42039 pour le partage d’application, définissez l’intervalle de ports comme suit: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="66e03-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="66e03-162">Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="66e03-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="66e03-163">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée:</span><span class="sxs-lookup"><span data-stu-id="66e03-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="66e03-164">Vous pouvez exécuter cette commande à partir de n’importe quelle fenêtre de commande exécutée sous informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="66e03-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="66e03-165">Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="66e03-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="66e03-166">Gardez à l’esprit que ces stratégies doivent être ciblées vers les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="66e03-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="66e03-167">Ils ne doivent pas être appliqués aux serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66e03-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="66e03-168">Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante:</span><span class="sxs-lookup"><span data-stu-id="66e03-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="66e03-169">Cliquez sur **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="66e03-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="66e03-170">Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="66e03-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="66e03-171">Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="66e03-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="66e03-172">Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="66e03-172">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="66e03-173">Une fois la nouvelle clé de Registre créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="66e03-173">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="66e03-174">Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**.</span><span class="sxs-lookup"><span data-stu-id="66e03-174">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="66e03-175">Après la création de la nouvelle valeur du Registre, tapez **ne pas utiliser NLA** , puis appuyez sur entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="66e03-175">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="66e03-176">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="66e03-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="66e03-177">Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66e03-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="66e03-178">Fermez l’éditeur du Registre, puis redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="66e03-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="66e03-179">Configuration de la qualité de service sur des ordinateurs dotés de plusieurs cartes réseau</span><span class="sxs-lookup"><span data-stu-id="66e03-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="66e03-180">Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, vous risquez de rencontrer des problèmes pour lesquels les valeurs DSCP apparaissent sous la forme de 0x00 au lieu de la valeur configurée.</span><span class="sxs-lookup"><span data-stu-id="66e03-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="66e03-181">Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs des cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé).</span><span class="sxs-lookup"><span data-stu-id="66e03-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="66e03-182">Dans les cas similaires, les valeurs DSCP seront balisées pour les adaptateurs qui peuvent accéder au domaine, mais ne seront pas balisés pour les cartes qui ne peuvent pas accéder au domaine.</span><span class="sxs-lookup"><span data-stu-id="66e03-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="66e03-183">Si vous souhaitez baliser les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre.</span><span class="sxs-lookup"><span data-stu-id="66e03-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="66e03-184">Pour cela, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="66e03-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="66e03-185">Cliquez sur **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="66e03-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="66e03-186">Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="66e03-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="66e03-187">Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="66e03-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="66e03-188">Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="66e03-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="66e03-189">Une fois la nouvelle clé créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="66e03-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="66e03-190">Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**.</span><span class="sxs-lookup"><span data-stu-id="66e03-190">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="66e03-191">Après la création de la nouvelle valeur du Registre, tapez **ne pas utiliser NLA** , puis appuyez sur entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="66e03-191">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="66e03-192">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="66e03-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="66e03-193">Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66e03-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="66e03-194">Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur pour que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="66e03-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

