---
title: 'Lync Server 2013 : configuration des stratégies de qualité de service pour les clients s’exécutant sur Windows 7 ou Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05835b74f12d5e2d28036b100fd84f207a64e67c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="3069d-102">Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients s’exécutant sur Windows 7 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="3069d-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3069d-103">_**Dernière modification de la rubrique :** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="3069d-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="3069d-104">En plus de spécifier des plages de ports pour les clients Lync, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="3069d-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="3069d-105">(Les stratégies de qualité de service créées pour les serveurs de conférence, d’application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Lync 2013 et Windows 7 ou Windows 8.</span><span class="sxs-lookup"><span data-stu-id="3069d-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="3069d-106">L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :</span><span class="sxs-lookup"><span data-stu-id="3069d-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3069d-107">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="3069d-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="3069d-108">Démarrage du port</span><span class="sxs-lookup"><span data-stu-id="3069d-108">Port Start</span></span></th>
<th><span data-ttu-id="3069d-109">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="3069d-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3069d-110">Audio</span><span class="sxs-lookup"><span data-stu-id="3069d-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="3069d-111">50020</span><span class="sxs-lookup"><span data-stu-id="3069d-111">50020</span></span></p></td>
<td><p><span data-ttu-id="3069d-112">vingtaine</span><span class="sxs-lookup"><span data-stu-id="3069d-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3069d-113">Vidéo</span><span class="sxs-lookup"><span data-stu-id="3069d-113">Video</span></span></p></td>
<td><p><span data-ttu-id="3069d-114">58000</span><span class="sxs-lookup"><span data-stu-id="3069d-114">58000</span></span></p></td>
<td><p><span data-ttu-id="3069d-115">vingtaine</span><span class="sxs-lookup"><span data-stu-id="3069d-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3069d-116">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="3069d-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3069d-117">42000</span><span class="sxs-lookup"><span data-stu-id="3069d-117">42000</span></span></p></td>
<td><p><span data-ttu-id="3069d-118">vingtaine</span><span class="sxs-lookup"><span data-stu-id="3069d-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3069d-119">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="3069d-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="3069d-120">42020</span><span class="sxs-lookup"><span data-stu-id="3069d-120">42020</span></span></p></td>
<td><p><span data-ttu-id="3069d-121">vingtaine</span><span class="sxs-lookup"><span data-stu-id="3069d-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3069d-122">Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 7 ou Windows 8, connectez-vous d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="3069d-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="3069d-123">Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **gestion des stratégies de groupe**), puis effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="3069d-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="3069d-124">Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="3069d-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="3069d-125">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.</span><span class="sxs-lookup"><span data-stu-id="3069d-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="3069d-126">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici**.</span><span class="sxs-lookup"><span data-stu-id="3069d-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="3069d-127">Dans la boîte de dialogue **nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Lync audio**), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3069d-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="3069d-128">Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="3069d-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="3069d-129">Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **Stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur la stratégie**, puis cliquez sur **Créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="3069d-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="3069d-130">Dans la boîte de dialogue **QoS basée** sur la stratégie, dans la page d’accueil, tapez un nom pour la nouvelle stratégie (par exemple, **Lync audio**) dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="3069d-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="3069d-131">Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**.</span><span class="sxs-lookup"><span data-stu-id="3069d-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="3069d-132">Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3069d-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="3069d-133">Sur la page suivante, sélectionnez **uniquement les applications avec ce nom d’exécutable** et entrez le nom **Lync. exe**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3069d-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="3069d-134">Ce paramètre indique à la stratégie de ne classer que le trafic correspondant à partir du client Lync.</span><span class="sxs-lookup"><span data-stu-id="3069d-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="3069d-135">Sur la troisième page, assurez-vous que **toutes les adresses IP source** et **toute adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3069d-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="3069d-136">Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.</span><span class="sxs-lookup"><span data-stu-id="3069d-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="3069d-137">Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**.</span><span class="sxs-lookup"><span data-stu-id="3069d-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="3069d-138">Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="3069d-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="3069d-139">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**.</span><span class="sxs-lookup"><span data-stu-id="3069d-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="3069d-140">Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="3069d-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="3069d-141">Par exemple, si vous avez réservé les ports 50020 via les ports 50039 pour le trafic audio, entrez la plage de ports au format suivant : **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="3069d-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="3069d-142">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3069d-142">Click **Finish**.</span></span>

<span data-ttu-id="3069d-143">Une fois que vous avez créé la stratégie de qualité de service pour l’audio, vous devez créer une deuxième stratégie pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="3069d-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="3069d-144">Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3069d-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="3069d-145">Utilisez un nom de stratégie différent (et unique) (par exemple, **vidéo Lync**).</span><span class="sxs-lookup"><span data-stu-id="3069d-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="3069d-146">Attribuez à la valeur DSCP la valeur **34** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="3069d-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="3069d-147">(Comme indiqué précédemment, il n’est pas nécessaire d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP différente de celle utilisée pour l’audio.)</span><span class="sxs-lookup"><span data-stu-id="3069d-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="3069d-148">Utilisez la plage de ports configurée précédemment pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="3069d-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="3069d-149">Par exemple, si vous avez réservé les ports 58000 à 58019 pour la vidéo, définissez la plage de ports comme suit : **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="3069d-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="3069d-150">Si vous décidez de créer une stratégie pour gérer le trafic du partage d’application, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3069d-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="3069d-151">Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="3069d-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="3069d-152">Attribuez à la valeur DSCP la valeur **24** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="3069d-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="3069d-153">(Encore une fois, cette valeur ne doit pas être égale à 24 ; elle doit simplement être différente des valeurs DSCP utilisées pour l’audio et la vidéo.)</span><span class="sxs-lookup"><span data-stu-id="3069d-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="3069d-154">Utilisez la plage de ports configurée précédemment pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="3069d-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="3069d-155">Par exemple, si vous avez réservé les ports 42000 à 42019 pour le partage d’application, définissez la plage de ports comme suit : **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="3069d-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="3069d-156">Pour une stratégie de transfert de fichiers :</span><span class="sxs-lookup"><span data-stu-id="3069d-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="3069d-157">Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="3069d-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="3069d-158">Définissez la valeur DSCP sur **14**.</span><span class="sxs-lookup"><span data-stu-id="3069d-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="3069d-159">(Encore une fois, cette valeur ne doit pas être 14 ; elle doit simplement être un code DSCP unique.)</span><span class="sxs-lookup"><span data-stu-id="3069d-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="3069d-160">Utiliser la plage de ports précédemment configurée pour l’application.</span><span class="sxs-lookup"><span data-stu-id="3069d-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="3069d-161">Par exemple, si vous avez réservé les ports 42020 à 42039 pour le partage d’application, définissez la plage de ports comme suit : **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="3069d-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="3069d-162">Les nouvelles stratégies que vous avez créées ne prendront effet qu’après l’actualisation de la stratégie de groupe sur vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="3069d-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="3069d-163">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :</span><span class="sxs-lookup"><span data-stu-id="3069d-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="3069d-164">Cette commande peut être exécutée à partir de n’importe quelle fenêtre de commande exécutée sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3069d-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="3069d-165">Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="3069d-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="3069d-166">Gardez à l’esprit que ces stratégies doivent être ciblées vers vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="3069d-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="3069d-167">Elles ne doivent pas être appliquées aux serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3069d-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="3069d-168">Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3069d-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="3069d-169">Pour ce faire, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3069d-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="3069d-170">Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="3069d-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="3069d-171">Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="3069d-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="3069d-p119">Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="3069d-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="3069d-p120">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="3069d-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="3069d-176">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="3069d-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="3069d-177">Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3069d-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="3069d-178">Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3069d-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="3069d-179">Configuration de la qualité de service sur des ordinateurs avec plusieurs cartes réseau</span><span class="sxs-lookup"><span data-stu-id="3069d-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="3069d-180">Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, vous pouvez parfois rencontrer des problèmes lorsque des valeurs DSCP apparaissent sous la forme 0x00 au lieu de la valeur configurée.</span><span class="sxs-lookup"><span data-stu-id="3069d-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="3069d-181">Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs cartes réseau ne peuvent pas accéder à votre domaine Active Directory (par exemple, si ces adaptateurs sont utilisés pour un réseau privé).</span><span class="sxs-lookup"><span data-stu-id="3069d-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="3069d-182">Dans ce cas, les valeurs DSCP seront balisées pour les cartes qui peuvent accéder au domaine, mais elles ne seront pas balisées pour les cartes qui ne peuvent pas accéder au domaine.</span><span class="sxs-lookup"><span data-stu-id="3069d-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="3069d-183">Si vous souhaitez marquer les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les adaptateurs qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre.</span><span class="sxs-lookup"><span data-stu-id="3069d-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="3069d-184">Pour cela, effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="3069d-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="3069d-185">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3069d-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="3069d-186">Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="3069d-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="3069d-187">Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="3069d-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="3069d-188">Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="3069d-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="3069d-189">Une fois la nouvelle clé créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="3069d-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="3069d-p125">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="3069d-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="3069d-192">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="3069d-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="3069d-193">Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3069d-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="3069d-194">Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur afin que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="3069d-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

