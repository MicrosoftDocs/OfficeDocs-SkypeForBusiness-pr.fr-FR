---
title: Configuration de plages de ports et d’une stratégie de qualité de service pour vos clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article décrit la configuration des plages de port pour vos clients et la configuration des stratégies de qualité de service dans Skype entreprise Server pour les clients exécutant Windows 10.
ms.openlocfilehash: 9a82a254ab5a01982e9f1d4bd3a994fd67c03615
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817423"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="e027f-103">Configuration de plages de ports et d’une politique de qualité de service pour vos clients dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e027f-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="e027f-104">Cet article décrit la configuration des plages de port pour vos clients et la configuration des stratégies de qualité de service dans Skype entreprise Server pour les clients exécutant Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e027f-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="e027f-105">Configurer des plages de ports</span><span class="sxs-lookup"><span data-stu-id="e027f-105">Configure port ranges</span></span>

<span data-ttu-id="e027f-106">Par défaut, les applications clientes Skype entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsque vous participez à une session de communication. en effet, les plages de port spécifiques ne sont pas activées automatiquement pour les clients.</span><span class="sxs-lookup"><span data-stu-id="e027f-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="e027f-107">Toutefois, pour pouvoir utiliser la qualité de service, vous devez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et transfert de fichier) à une série de plages de ports uniques.</span><span class="sxs-lookup"><span data-stu-id="e027f-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="e027f-108">Pour ce faire, vous pouvez utiliser l’applet de passe Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e027f-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="e027f-109">Les utilisateurs finaux ne peuvent pas apporter ces modifications.</span><span class="sxs-lookup"><span data-stu-id="e027f-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="e027f-110">Les modifications de port ne peuvent être effectuées que par les administrateurs utilisant l’applet de cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e027f-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="e027f-111">Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="e027f-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="e027f-112">En supposant que vous n’avez apporté aucune modification à vos paramètres de conférence depuis que vous avez installé Skype entreprise Server, vous devez obtenir des informations sur les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="e027f-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="e027f-113">Si vous observez de près la sortie précédente, vous verrez deux points importants.</span><span class="sxs-lookup"><span data-stu-id="e027f-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="e027f-114">Tout d’abord, la propriété ClientMediaPortRangeEnabled est définie sur false :</span><span class="sxs-lookup"><span data-stu-id="e027f-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="e027f-115">C’est un point important, car lorsque cette propriété est définie sur false, les clients Skype entreprise utiliseront tout port disponible entre les ports 1024 et 65535 lors d’une session de communication ; C’est vrai, quels que soient les autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="e027f-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="e027f-116">Si vous souhaitez restreindre l’utilisation à un ensemble spécifique de ports (ce que vous voulez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de port de média client.</span><span class="sxs-lookup"><span data-stu-id="e027f-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="e027f-117">Vous pouvez effectuer cette opération à l’aide de la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="e027f-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="e027f-118">La commande précédente permet d’activer les plages de port de média client pour la collection globale de paramètres de configuration de conférence. Toutefois, ces paramètres peuvent également être appliqués à l’étendue du site et/ou à l’étendue du service (pour le service du serveur de conférence uniquement).</span><span class="sxs-lookup"><span data-stu-id="e027f-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="e027f-119">Pour activer les plages de port de média client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration :</span><span class="sxs-lookup"><span data-stu-id="e027f-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="e027f-120">Vous pouvez également utiliser cette commande pour activer simultanément les plages de ports pour tous les paramètres de configuration de la Conférence :</span><span class="sxs-lookup"><span data-stu-id="e027f-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="e027f-121">Le deuxième élément important que vous remarquerez est que la sortie de l’exemple indique que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques :</span><span class="sxs-lookup"><span data-stu-id="e027f-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="e027f-122">Pour implémenter QoS, chacune de ces plages de port doit être unique.</span><span class="sxs-lookup"><span data-stu-id="e027f-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="e027f-123">Par exemple, vous pouvez configurer les plages de ports comme suit :</span><span class="sxs-lookup"><span data-stu-id="e027f-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e027f-124">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="e027f-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="e027f-125">Début du port</span><span class="sxs-lookup"><span data-stu-id="e027f-125">Port Start</span></span></th>
<th><span data-ttu-id="e027f-126">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="e027f-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e027f-127">Audio</span><span class="sxs-lookup"><span data-stu-id="e027f-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="e027f-128">50020</span><span class="sxs-lookup"><span data-stu-id="e027f-128">50020</span></span></p></td>
<td><p><span data-ttu-id="e027f-129">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e027f-130">Vidéo</span><span class="sxs-lookup"><span data-stu-id="e027f-130">Video</span></span></p></td>
<td><p><span data-ttu-id="e027f-131">58000</span><span class="sxs-lookup"><span data-stu-id="e027f-131">58000</span></span></p></td>
<td><p><span data-ttu-id="e027f-132">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e027f-133">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="e027f-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="e027f-134">42000</span><span class="sxs-lookup"><span data-stu-id="e027f-134">42000</span></span></p></td>
<td><p><span data-ttu-id="e027f-135">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e027f-136">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="e027f-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="e027f-137">42020</span><span class="sxs-lookup"><span data-stu-id="e027f-137">42020</span></span></p></td>
<td><p><span data-ttu-id="e027f-138">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e027f-139">Dans le tableau ci-dessus, les plages de port client représentent un sous-ensemble des plages de ports configurées pour vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="e027f-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="e027f-140">Par exemple, sur les serveurs, le partage d’application a été configuré de manière à utiliser les ports 40803 à 49151 ; sur les ordinateurs clients, le partage d’application est configuré de manière à utiliser les ports 42000 à 42019.</span><span class="sxs-lookup"><span data-stu-id="e027f-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="e027f-141">C’est aussi essentiellement pour faciliter l’administration de la qualité de service (QoS) : les ports clients n’ont pas besoin de représenter un sous-ensemble de ports utilisés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="e027f-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="e027f-142">(Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application à utiliser, par exemple, les ports 10000 à 10019.) Néanmoins, nous vous conseillons de faire en sorte que les plages de port de votre client constituent un sous-ensemble de vos plages de port serveur.</span><span class="sxs-lookup"><span data-stu-id="e027f-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="e027f-143">Par ailleurs, vous avez peut-être remarqué que les ports 8348 étaient mis de côté pour le partage d’application sur les serveurs, mais que seuls 20 ports étaient mis de côté pour le partage d’application sur les clients.</span><span class="sxs-lookup"><span data-stu-id="e027f-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="e027f-144">C’est également recommandé, mais n’est pas une règle matérielle et rapide.</span><span class="sxs-lookup"><span data-stu-id="e027f-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="e027f-145">En règle générale, vous pouvez considérer chaque port disponible pour représenter une seule session de communication : Si vous disposez de ports 100 disponibles dans une plage de port, cela signifie que l’ordinateur en question peut, au plus, des sessions de communication 100 à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e027f-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="e027f-146">Étant donné que les serveurs seront susceptibles de participer dans de nombreuses conversations qu’aux clients, il est préférable d’ouvrir de nombreux ports supplémentaires sur les serveurs plutôt que sur les clients.</span><span class="sxs-lookup"><span data-stu-id="e027f-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="e027f-147">La mise en place de 20 ports pour le partage d’application sur un client implique qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, en même temps.</span><span class="sxs-lookup"><span data-stu-id="e027f-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="e027f-148">Cela devrait s’avérer suffisant pour la plupart de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e027f-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="e027f-149">Pour affecter les plages de port précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande suivante de Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="e027f-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="e027f-150">Vous pouvez utiliser cette commande pour affecter les mêmes plages de ports à tous les paramètres de configuration de la Conférence :</span><span class="sxs-lookup"><span data-stu-id="e027f-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="e027f-151">Les utilisateurs individuels doivent se déconnecter de Skype entreprise, puis se reconnecter pour que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="e027f-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="e027f-152">Vous pouvez également activer les plages de port de média client, puis les affecter à l’aide d’une seule commande.</span><span class="sxs-lookup"><span data-stu-id="e027f-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="e027f-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e027f-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="e027f-154">Configurer des stratégies de qualité de service pour les clients qui s’exécutent sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="e027f-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="e027f-155">En plus de spécifier des plages de port destinées aux clients Skype entreprise, vous devez également créer des politiques de qualité de service distinctes qui seront appliquées aux ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="e027f-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="e027f-156">(La qualité de service créée pour les serveurs de conférence, d’application et de médiation ne doit pas être appliquée aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Skype entreprise et Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e027f-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="e027f-157">L’exemple suivant utilise ce jeu de plages de ports pour créer une stratégie audio et une stratégie de vidéo :</span><span class="sxs-lookup"><span data-stu-id="e027f-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e027f-158">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="e027f-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="e027f-159">Début du port</span><span class="sxs-lookup"><span data-stu-id="e027f-159">Port Start</span></span></th>
<th><span data-ttu-id="e027f-160">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="e027f-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e027f-161">Audio</span><span class="sxs-lookup"><span data-stu-id="e027f-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="e027f-162">50020</span><span class="sxs-lookup"><span data-stu-id="e027f-162">50020</span></span></p></td>
<td><p><span data-ttu-id="e027f-163">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e027f-164">Vidéo</span><span class="sxs-lookup"><span data-stu-id="e027f-164">Video</span></span></p></td>
<td><p><span data-ttu-id="e027f-165">58000</span><span class="sxs-lookup"><span data-stu-id="e027f-165">58000</span></span></p></td>
<td><p><span data-ttu-id="e027f-166">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e027f-167">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="e027f-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="e027f-168">42000</span><span class="sxs-lookup"><span data-stu-id="e027f-168">42000</span></span></p></td>
<td><p><span data-ttu-id="e027f-169">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e027f-170">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="e027f-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="e027f-171">42020</span><span class="sxs-lookup"><span data-stu-id="e027f-171">42020</span></span></p></td>
<td><p><span data-ttu-id="e027f-172">CX3-20</span><span class="sxs-lookup"><span data-stu-id="e027f-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e027f-173">Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 10, vous devez d’abord vous connecter à un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="e027f-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="e027f-174">Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e027f-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="e027f-175">Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="e027f-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="e027f-176">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.</span><span class="sxs-lookup"><span data-stu-id="e027f-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="e027f-177">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.</span><span class="sxs-lookup"><span data-stu-id="e027f-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="e027f-178">Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e027f-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="e027f-179">Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="e027f-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="e027f-180">Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="e027f-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="e027f-181">Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="e027f-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="e027f-182">Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**.</span><span class="sxs-lookup"><span data-stu-id="e027f-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="e027f-183">Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e027f-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="e027f-184">Dans la page suivante, sélectionnez **uniquement les applications ayant ce nom d’exécutable**, entrez **Lync. exe** comme nom, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e027f-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="e027f-185">Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant à partir du client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="e027f-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="e027f-186">Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e027f-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="e027f-187">Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.</span><span class="sxs-lookup"><span data-stu-id="e027f-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="e027f-188">Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** .</span><span class="sxs-lookup"><span data-stu-id="e027f-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="e027f-189">Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Skype entreprise Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="e027f-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="e027f-190">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**.</span><span class="sxs-lookup"><span data-stu-id="e027f-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="e027f-191">Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="e027f-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="e027f-192">Par exemple, si vous avez réservé ports 50020 via ports 50039 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="e027f-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="e027f-193">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e027f-193">Click **Finish**.</span></span>

<span data-ttu-id="e027f-194">Une fois que vous avez créé la stratégie QoS pour le son, vous devez créer une deuxième stratégie pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="e027f-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="e027f-195">Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e027f-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="e027f-196">Utilisez un nom de stratégie différent (et unique).</span><span class="sxs-lookup"><span data-stu-id="e027f-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="e027f-197">Définissez la valeur DSCP sur **34** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="e027f-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="e027f-198">(Comme indiqué précédemment, vous n’avez pas besoin d’utiliser la valeur DSCP 34 ; il vous suffit d’affecter une valeur DSCP différente de celle utilisée pour l’audio.)</span><span class="sxs-lookup"><span data-stu-id="e027f-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="e027f-199">Utilisez la plage de ports configurée précédemment pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="e027f-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="e027f-200">Par exemple, si vous avez réservé ports 58000 à 58019 pour la vidéo, définissez l’intervalle de ports comme suit : **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="e027f-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="e027f-201">Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, effectuez les substitutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e027f-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="e027f-202">Utilisez un nom de stratégie différent (et unique) (par exemple, **partage d’application Skype entreprise Server**).</span><span class="sxs-lookup"><span data-stu-id="e027f-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="e027f-203">Définissez la valeur DSCP sur **24** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="e027f-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="e027f-204">(De nouveau, cette valeur ne doit pas être de 24 ; il doit simplement être différent des valeurs DSCP utilisées pour l’audio et la vidéo.)</span><span class="sxs-lookup"><span data-stu-id="e027f-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="e027f-205">Utilisez la plage de ports configurée précédemment pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="e027f-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="e027f-206">Par exemple, si vous avez réservé ports 42000 à 42019 pour le partage d’application, définissez l’intervalle de ports comme suit : **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="e027f-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="e027f-207">Pour une stratégie de transfert de fichiers :</span><span class="sxs-lookup"><span data-stu-id="e027f-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="e027f-208">Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Skype entreprise Server**).</span><span class="sxs-lookup"><span data-stu-id="e027f-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="e027f-209">Définissez la valeur DSCP sur **14**.</span><span class="sxs-lookup"><span data-stu-id="e027f-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="e027f-210">(De nouveau, cette valeur ne doit pas être 14 ; il doit simplement s’agir d’un code DSCP unique.)</span><span class="sxs-lookup"><span data-stu-id="e027f-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="e027f-211">Utilisez la plage de port précédemment configurée pour l’application.</span><span class="sxs-lookup"><span data-stu-id="e027f-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="e027f-212">Par exemple, si vous avez réservé ports 42020 à 42039 pour le partage d’application, définissez l’intervalle de ports comme suit : **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="e027f-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="e027f-213">Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="e027f-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="e027f-214">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée :</span><span class="sxs-lookup"><span data-stu-id="e027f-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="e027f-215">Vous pouvez exécuter cette commande à partir de n’importe quelle fenêtre de commande exécutée sous informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="e027f-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="e027f-216">Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="e027f-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="e027f-217">Gardez à l’esprit que ces stratégies doivent être ciblées vers les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="e027f-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="e027f-218">Ils ne doivent pas être appliqués aux serveurs exécutant Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e027f-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="e027f-219">Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="e027f-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="e027f-220">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="e027f-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="e027f-221">Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="e027f-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="e027f-222">Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="e027f-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="e027f-223">Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="e027f-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="e027f-224">Une fois la nouvelle clé de Registre créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="e027f-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="e027f-225">Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**.</span><span class="sxs-lookup"><span data-stu-id="e027f-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="e027f-226">Une fois la nouvelle valeur du Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="e027f-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="e027f-227">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="e027f-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="e027f-228">Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e027f-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="e027f-229">Fermez l’éditeur du Registre et EBOOT votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e027f-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="e027f-230">Configurer la qualité de service sur des ordinateurs dotés de plusieurs cartes réseau</span><span class="sxs-lookup"><span data-stu-id="e027f-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="e027f-231">Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, il est possible que vous rencontriez des problèmes de valeurs DSCP au lieu de la valeur configurée.</span><span class="sxs-lookup"><span data-stu-id="e027f-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="e027f-232">Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs des cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé).</span><span class="sxs-lookup"><span data-stu-id="e027f-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="e027f-233">Dans les cas similaires, les valeurs DSCP seront balisées pour les adaptateurs qui peuvent accéder au domaine, mais ne seront pas balisés pour les cartes qui ne peuvent pas accéder au domaine.</span><span class="sxs-lookup"><span data-stu-id="e027f-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="e027f-234">Si vous souhaitez baliser les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre.</span><span class="sxs-lookup"><span data-stu-id="e027f-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="e027f-235">Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e027f-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="e027f-236">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="e027f-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="e027f-237">Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="e027f-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="e027f-238">Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="e027f-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="e027f-239">Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="e027f-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="e027f-240">Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="e027f-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="e027f-241">Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**.</span><span class="sxs-lookup"><span data-stu-id="e027f-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="e027f-242">Une fois la nouvelle valeur du Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="e027f-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="e027f-243">Double-cliquez sur **ne pas utiliser NLA**.</span><span class="sxs-lookup"><span data-stu-id="e027f-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="e027f-244">Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e027f-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="e027f-245">Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="e027f-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="e027f-246">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e027f-246">See also</span></span>

[<span data-ttu-id="e027f-247">Créer un objet de stratégie de groupe dans Windows 10</span><span class="sxs-lookup"><span data-stu-id="e027f-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
