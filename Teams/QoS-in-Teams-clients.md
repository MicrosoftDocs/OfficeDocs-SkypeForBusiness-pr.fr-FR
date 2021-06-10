---
title: Implémenter la qualité de service (QoS) dans Microsoft Teams clients
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment utiliser la qualité de service (QoS) pour optimiser le trafic réseau du client Microsoft Teams bureau.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094782"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="a5e51-103">Implémenter la qualité de service (QoS) dans Microsoft Teams clients</span><span class="sxs-lookup"><span data-stu-id="a5e51-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="a5e51-104">Vous pouvez utiliser la qualité de service basée sur une stratégie au sein d’une stratégie de groupe pour définir la plage de ports source pour la valeur DSCP prédéfinée dans le client Teams client.</span><span class="sxs-lookup"><span data-stu-id="a5e51-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="a5e51-105">Les plages de ports spécifiées dans le tableau suivant sont un point de départ pour créer une stratégie pour chaque charge de travail.</span><span class="sxs-lookup"><span data-stu-id="a5e51-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="a5e51-106">*Tableau 1. Plages de ports initiales recommandées*</span><span class="sxs-lookup"><span data-stu-id="a5e51-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="a5e51-107">Type de trafic média</span><span class="sxs-lookup"><span data-stu-id="a5e51-107">Media traffic type</span></span>| <span data-ttu-id="a5e51-108">Plage de port source du client </span><span class="sxs-lookup"><span data-stu-id="a5e51-108">Client source port range</span></span> |<span data-ttu-id="a5e51-109">Protocole</span><span class="sxs-lookup"><span data-stu-id="a5e51-109">Protocol</span></span>|<span data-ttu-id="a5e51-110">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="a5e51-110">DSCP value</span></span>|<span data-ttu-id="a5e51-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="a5e51-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="a5e51-112">Audio</span><span class="sxs-lookup"><span data-stu-id="a5e51-112">Audio</span></span>| <span data-ttu-id="a5e51-113">Entre 50 000 et 50 019</span><span class="sxs-lookup"><span data-stu-id="a5e51-113">50,000–50,019</span></span>|<span data-ttu-id="a5e51-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a5e51-114">TCP/UDP</span></span>|<span data-ttu-id="a5e51-115">46</span><span class="sxs-lookup"><span data-stu-id="a5e51-115">46</span></span>|<span data-ttu-id="a5e51-116">Acheminement accéléré (EF)</span><span class="sxs-lookup"><span data-stu-id="a5e51-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="a5e51-117">Vidéo</span><span class="sxs-lookup"><span data-stu-id="a5e51-117">Video</span></span>| <span data-ttu-id="a5e51-118">50 020–50 039</span><span class="sxs-lookup"><span data-stu-id="a5e51-118">50,020–50,039</span></span>|<span data-ttu-id="a5e51-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a5e51-119">TCP/UDP</span></span>|<span data-ttu-id="a5e51-120">34</span><span class="sxs-lookup"><span data-stu-id="a5e51-120">34</span></span>|<span data-ttu-id="a5e51-121">Acheminement assuré (AF41)</span><span class="sxs-lookup"><span data-stu-id="a5e51-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="a5e51-122">Partage d’application/d'écran</span><span class="sxs-lookup"><span data-stu-id="a5e51-122">Application/Screen Sharing</span></span>| <span data-ttu-id="a5e51-123">50 040–50 059</span><span class="sxs-lookup"><span data-stu-id="a5e51-123">50,040–50,059</span></span>|<span data-ttu-id="a5e51-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a5e51-124">TCP/UDP</span></span>|<span data-ttu-id="a5e51-125">18</span><span class="sxs-lookup"><span data-stu-id="a5e51-125">18</span></span>|<span data-ttu-id="a5e51-126">Transfert garanti (AF21)</span><span class="sxs-lookup"><span data-stu-id="a5e51-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="a5e51-127">Lorsque possible, configurez les paramètres de QoS basés sur une stratégie dans un objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="a5e51-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="a5e51-128">Les étapes suivantes sont très semblables à la configuration des plages de ports et à une stratégie de qualité de service pour vos clients sur [Skype Entreprise Server,](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)qui présente des détails supplémentaires qui peuvent ne pas être nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a5e51-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="a5e51-129">Pour créer une stratégie audio QoS pour des ordinateurs Windows 10 joints à un domaine, connectez-vous tout d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="a5e51-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="a5e51-130">Ouvrez la gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur Outils d’administration, puis cliquez sur Gestion des stratégies de groupe), puis complétez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5e51-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="a5e51-131">Dans la gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="a5e51-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a5e51-132">Par exemple, si tous vos ordinateurs clients sont situés dans une ou plusieurs **clients,** la nouvelle stratégie doit être créée dans l’ou Clients.</span><span class="sxs-lookup"><span data-stu-id="a5e51-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="a5e51-133">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un GPO dans ce **domaine, puis lier ici.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="a5e51-134">Dans la **boîte de dialogue** Nouveau objet de stratégie de groupe, tapez un nom pour le nouvel objet de stratégie de groupe dans la zone Nom, puis cliquez sur **OK.** </span><span class="sxs-lookup"><span data-stu-id="a5e51-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="a5e51-135">Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="a5e51-136">Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration** ordinateur, développez **Windows Paramètres,** cliquez avec le bouton droit sur **QoS** basé sur une stratégie, puis cliquez sur **Créer une stratégie.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="a5e51-137">Dans la **boîte de dialogue QoS** basée sur une stratégie, dans la page d’ouverture, tapez le nom de la nouvelle stratégie dans la **zone** Nom.</span><span class="sxs-lookup"><span data-stu-id="a5e51-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="a5e51-138">Sélectionnez **Spécifier la valeur DSCP** et définissez la valeur **sur 46.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a5e51-139">Laissez **Spécifier la fréquence de limitation** sortante non sélectionné, puis cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="a5e51-140">Sur la page suivante, sélectionnez Uniquement les applications avec ce nom **exécutable,** entrez le **Teams.exe,** puis cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="a5e51-141">Ce paramètre indique à la stratégie de ne hiérarchiser que les trafics correspondants en provenance Teams client.</span><span class="sxs-lookup"><span data-stu-id="a5e51-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="a5e51-142">Dans la troisième page, assurez-vous que les deux adresses **IP source** et N’importe quelle adresse IP de **destination** sont sélectionnées, puis cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="a5e51-143">Ces deux paramètres assurent la gestion des paquets, quel que soit l’ordinateur (adresse IP) qui a envoyé les paquets et le ou les ordinateurs (adresses IP) qui recevront les paquets.</span><span class="sxs-lookup"><span data-stu-id="a5e51-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="a5e51-144">Dans la page 4, sélectionnez TCP et **UDP** dans le protocole Sélectionnez le protocole que cette stratégie **QoS** s’applique à la liste de listes bas.</span><span class="sxs-lookup"><span data-stu-id="a5e51-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="a5e51-145">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés.</span><span class="sxs-lookup"><span data-stu-id="a5e51-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="a5e51-146">Sous **l’en-tête Spécifiez le numéro du port source,** **sélectionnez À partir de ce port ou plage source.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="a5e51-147">Dans la zone de texte d’accompagnement, tapez la plage de ports réservée aux transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="a5e51-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a5e51-148">Par exemple, si vous avez réservé des ports 50000 à ports 50019 pour le trafic audio, entrez la plage de ports en utilisant ce format : **50000:50019.**</span><span class="sxs-lookup"><span data-stu-id="a5e51-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="a5e51-149">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a5e51-149">Click **Finish**.</span></span>

1. <span data-ttu-id="a5e51-150">Répétez les étapes 5 à 10 pour créer des stratégies pour le partage de vidéo et d’application/bureau en remplaçant les valeurs appropriées aux étapes 6 et 10.</span><span class="sxs-lookup"><span data-stu-id="a5e51-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="a5e51-151">Les nouvelles stratégies que vous avez créées ne prennent pas effet tant que la stratégie de groupe n’a pas été actualisée sur vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="a5e51-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="a5e51-152">Bien que la stratégie de groupe soit actualisée régulièrement, vous pouvez forcer une actualisation immédiate en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5e51-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="a5e51-153">Sur chaque ordinateur pour lequel vous voulez actualiser la stratégie de groupe, ouvrez une invite de commandes en tant qu’administrateur *(exécuter en tant qu’administrateur).*</span><span class="sxs-lookup"><span data-stu-id="a5e51-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="a5e51-154">À l’invite de commandes, entrez</span><span class="sxs-lookup"><span data-stu-id="a5e51-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="a5e51-155">Vérifier les marquages DSCP dans l’objet de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="a5e51-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="a5e51-156">Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5e51-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="a5e51-157">Ouvrez une invite de commandes en tant qu’administrateur *(exécuter en tant qu’administrateur).*</span><span class="sxs-lookup"><span data-stu-id="a5e51-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="a5e51-158">À l’invite de commandes, entrez</span><span class="sxs-lookup"><span data-stu-id="a5e51-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="a5e51-159">Cela génère un rapport sur les os de groupe appliqués et l’envoie à un fichier texte nommé *gp.txt.*</span><span class="sxs-lookup"><span data-stu-id="a5e51-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="a5e51-160">Pour un rapport HTML plus lisible nommé *gp.html,* entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a5e51-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="a5e51-161">Dans le fichier généré, recherchez l’en-tête Objets de stratégie de groupe **appliqués** et vérifiez que les noms des objets de stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.</span><span class="sxs-lookup"><span data-stu-id="a5e51-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="a5e51-162">Ouvrez l’Éditeur du Registre, puis allez à</span><span class="sxs-lookup"><span data-stu-id="a5e51-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="a5e51-163">Politiques \_ logicielles LOCALES HKEY pour Microsoft \_ Windows \\ \\ \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="a5e51-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="a5e51-164">Vérifiez les valeurs des entrées de Registre répertoriées dans le tableau 2.</span><span class="sxs-lookup"><span data-stu-id="a5e51-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="a5e51-165">*Tableau 2. Valeurs des Windows de Registre pour QoS*</span><span class="sxs-lookup"><span data-stu-id="a5e51-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="a5e51-166">Nom</span><span class="sxs-lookup"><span data-stu-id="a5e51-166">Name</span></span>          |  <span data-ttu-id="a5e51-167">Type</span><span class="sxs-lookup"><span data-stu-id="a5e51-167">Type</span></span>  |    <span data-ttu-id="a5e51-168">Données</span><span class="sxs-lookup"><span data-stu-id="a5e51-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="a5e51-169">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="a5e51-169">Application Name</span></span>    | <span data-ttu-id="a5e51-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-170">REG_SZ</span></span> |  <span data-ttu-id="a5e51-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="a5e51-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="a5e51-172">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="a5e51-172">DSCP Value</span></span>       | <span data-ttu-id="a5e51-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-173">REG_SZ</span></span> |     <span data-ttu-id="a5e51-174">46</span><span class="sxs-lookup"><span data-stu-id="a5e51-174">46</span></span>      |
   |        <span data-ttu-id="a5e51-175">Adresse IP locale</span><span class="sxs-lookup"><span data-stu-id="a5e51-175">Local IP</span></span>        | <span data-ttu-id="a5e51-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="a5e51-177">Longueur du préfixe IP local</span><span class="sxs-lookup"><span data-stu-id="a5e51-177">Local IP Prefix Length</span></span> | <span data-ttu-id="a5e51-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="a5e51-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="a5e51-179">Local Port</span></span>       | <span data-ttu-id="a5e51-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-180">REG_SZ</span></span> | <span data-ttu-id="a5e51-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="a5e51-181">50000-50019</span></span> |
   |        <span data-ttu-id="a5e51-182">Protocol (Protocole)</span><span class="sxs-lookup"><span data-stu-id="a5e51-182">Protocol</span></span>        | <span data-ttu-id="a5e51-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="a5e51-184">Adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="a5e51-184">Remote IP</span></span>        | <span data-ttu-id="a5e51-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="a5e51-186">Préfixe IP distant</span><span class="sxs-lookup"><span data-stu-id="a5e51-186">Remote IP Prefix</span></span>    | <span data-ttu-id="a5e51-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="a5e51-188">Port distant</span><span class="sxs-lookup"><span data-stu-id="a5e51-188">Remote Port</span></span>       | <span data-ttu-id="a5e51-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="a5e51-190">Limiter les taux</span><span class="sxs-lookup"><span data-stu-id="a5e51-190">Throttle Rate</span></span>      | <span data-ttu-id="a5e51-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e51-191">REG_SZ</span></span> |     <span data-ttu-id="a5e51-192">-1</span><span class="sxs-lookup"><span data-stu-id="a5e51-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="a5e51-193">Vérifiez que la valeur de l’entrée Nom de l’application est correcte pour le client que vous utilisez, et vérifiez que les entrées de port DSCP et de port local reflètent les paramètres dans l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="a5e51-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a5e51-194">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="a5e51-194">Related topics</span></span>

[<span data-ttu-id="a5e51-195">Implémenter la qualité de service (QoS) dans Teams</span><span class="sxs-lookup"><span data-stu-id="a5e51-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)