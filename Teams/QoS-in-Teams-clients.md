---
title: Mise en œuvre de la qualité de service (QoS) pour les clients Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment utiliser la qualité de service (QoS) pour optimiser le trafic réseau pour le client de bureau Microsoft Teams.
ms.custom: seo-marvel-mar2020
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80b9257abbbb873b30367f9d430e9a8d155cda09
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085530"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="47675-103">Mise en œuvre de la qualité de service (QoS) pour les clients Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="47675-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="47675-104">Vous pouvez utiliser la qualité de service (QoS) basée sur les stratégies dans une stratégie de groupe pour définir la plage de ports sources pour la valeur DSCP prédéfinie dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="47675-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="47675-105">Les plages de port spécifiées dans le tableau suivant constituent un point de départ pour créer une stratégie pour chaque charge de travail.</span><span class="sxs-lookup"><span data-stu-id="47675-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="47675-106">*Tableau 1. Plages de port initiales recommandées*</span><span class="sxs-lookup"><span data-stu-id="47675-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="47675-107">Type de trafic média</span><span class="sxs-lookup"><span data-stu-id="47675-107">Media traffic type</span></span>| <span data-ttu-id="47675-108">Plage de port source du client </span><span class="sxs-lookup"><span data-stu-id="47675-108">Client source port range</span></span> |<span data-ttu-id="47675-109">Protocole</span><span class="sxs-lookup"><span data-stu-id="47675-109">Protocol</span></span>|<span data-ttu-id="47675-110">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="47675-110">DSCP value</span></span>|<span data-ttu-id="47675-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="47675-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="47675-112">Audio</span><span class="sxs-lookup"><span data-stu-id="47675-112">Audio</span></span>| <span data-ttu-id="47675-113">Entre 50 000 et 50 019</span><span class="sxs-lookup"><span data-stu-id="47675-113">50,000–50,019</span></span>|<span data-ttu-id="47675-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="47675-114">TCP/UDP</span></span>|<span data-ttu-id="47675-115">46</span><span class="sxs-lookup"><span data-stu-id="47675-115">46</span></span>|<span data-ttu-id="47675-116">Acheminement accéléré (EF)</span><span class="sxs-lookup"><span data-stu-id="47675-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="47675-117">Vidéo</span><span class="sxs-lookup"><span data-stu-id="47675-117">Video</span></span>| <span data-ttu-id="47675-118">50 020–50 039</span><span class="sxs-lookup"><span data-stu-id="47675-118">50,020–50,039</span></span>|<span data-ttu-id="47675-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="47675-119">TCP/UDP</span></span>|<span data-ttu-id="47675-120">34</span><span class="sxs-lookup"><span data-stu-id="47675-120">34</span></span>|<span data-ttu-id="47675-121">Acheminement assuré (AF41)</span><span class="sxs-lookup"><span data-stu-id="47675-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="47675-122">Partage d’application/d'écran</span><span class="sxs-lookup"><span data-stu-id="47675-122">Application/Screen Sharing</span></span>| <span data-ttu-id="47675-123">50 040–50 059</span><span class="sxs-lookup"><span data-stu-id="47675-123">50,040–50,059</span></span>|<span data-ttu-id="47675-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="47675-124">TCP/UDP</span></span>|<span data-ttu-id="47675-125">19</span><span class="sxs-lookup"><span data-stu-id="47675-125">18</span></span>|<span data-ttu-id="47675-126">Transfert garanti (AF21)</span><span class="sxs-lookup"><span data-stu-id="47675-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="47675-127">Dans la mesure du possible, vous pouvez configurer les paramètres de QoS basée sur une stratégie au sein d’un objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="47675-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="47675-128">Les étapes suivantes sont similaires à la [configuration de plages de ports et d’une politique de qualité de service pour vos clients sur Skype entreprise Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui comporte des informations supplémentaires qui peuvent ne pas être nécessaires.</span><span class="sxs-lookup"><span data-stu-id="47675-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="47675-129">Pour créer une stratégie audio QoS pour des ordinateurs Windows 10 liés à un domaine, vous devez d’abord vous connecter à un ordinateur sur lequel est installée la gestion des stratégies de groupe.</span><span class="sxs-lookup"><span data-stu-id="47675-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="47675-130">Ouvrez gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur outils d’administration, cliquez sur gestion des stratégies de groupe), puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="47675-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="47675-131">Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="47675-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="47675-132">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **clients**, la nouvelle stratégie doit être créée dans l’unité d’organisation clients.</span><span class="sxs-lookup"><span data-stu-id="47675-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="47675-133">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.</span><span class="sxs-lookup"><span data-stu-id="47675-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="47675-134">Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="47675-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="47675-135">Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="47675-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="47675-136">Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="47675-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="47675-137">Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="47675-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="47675-138">Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**.</span><span class="sxs-lookup"><span data-stu-id="47675-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="47675-139">Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="47675-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="47675-140">Sur la page suivante, sélectionnez **uniquement les applications ayant ce nom d’exécutable** , entrez le nom **Teams.exe**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="47675-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="47675-141">Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant du client Teams.</span><span class="sxs-lookup"><span data-stu-id="47675-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="47675-142">Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="47675-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="47675-143">Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé les paquets et de l’ordinateur (adresse IP) recevant les paquets.</span><span class="sxs-lookup"><span data-stu-id="47675-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="47675-144">Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** .</span><span class="sxs-lookup"><span data-stu-id="47675-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="47675-145">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés.</span><span class="sxs-lookup"><span data-stu-id="47675-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="47675-146">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**.</span><span class="sxs-lookup"><span data-stu-id="47675-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="47675-147">Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="47675-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="47675-148">Par exemple, si vous avez réservé ports 50000 via ports 50019 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="47675-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="47675-149">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="47675-149">Click **Finish**.</span></span>

1. <span data-ttu-id="47675-150">Répétez les étapes 5-10 pour créer des stratégies pour la vidéo et le partage de bureau et d’application</span><span class="sxs-lookup"><span data-stu-id="47675-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="47675-151">Les nouvelles stratégies que vous avez créées ne prennent effet qu’après la réactualisation de la stratégie de groupe sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="47675-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="47675-152">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="47675-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="47675-153">Sur chaque ordinateur pour lequel vous voulez actualiser une stratégie de groupe, ouvrez une invite de commandes en tant qu’administrateur (*exécuter en tant qu’administrateur*).</span><span class="sxs-lookup"><span data-stu-id="47675-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="47675-154">À l’invite de commandes, entrez</span><span class="sxs-lookup"><span data-stu-id="47675-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="47675-155">Vérifier les marquages DSCP dans l’objet de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="47675-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="47675-156">Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="47675-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="47675-157">Ouvrez une invite de commandes en tant qu’administrateur (*exécuter en tant qu’administrateur*).</span><span class="sxs-lookup"><span data-stu-id="47675-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="47675-158">À l’invite de commandes, entrez</span><span class="sxs-lookup"><span data-stu-id="47675-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="47675-159">Cette opération génère un rapport des objets de stratégie de groupe appliqués et les envoie à un fichier texte nommé *gp.txt*.</span><span class="sxs-lookup"><span data-stu-id="47675-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="47675-160">Pour un rapport HTML plus lisible intitulé *gp.html*, entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="47675-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="47675-161">Dans le fichier généré, recherchez le titre **appliqué objets de stratégie de groupe** , puis vérifiez que les noms des objets de stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.</span><span class="sxs-lookup"><span data-stu-id="47675-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="47675-162">Ouvrez l’éditeur du Registre et accédez à</span><span class="sxs-lookup"><span data-stu-id="47675-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="47675-163">HKEY \_ stratégies de logiciels de l' \_ ordinateur local \\ \\ \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="47675-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="47675-164">Vérifiez les valeurs des entrées de registre indiquées dans le tableau 2.</span><span class="sxs-lookup"><span data-stu-id="47675-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="47675-165">*Tableau 2. Valeurs pour les entrées de Registre Windows pour QoS*</span><span class="sxs-lookup"><span data-stu-id="47675-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="47675-166">Nom</span><span class="sxs-lookup"><span data-stu-id="47675-166">Name</span></span>          |  <span data-ttu-id="47675-167">Type</span><span class="sxs-lookup"><span data-stu-id="47675-167">Type</span></span>  |    <span data-ttu-id="47675-168">Données</span><span class="sxs-lookup"><span data-stu-id="47675-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="47675-169">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="47675-169">Application Name</span></span>    | <span data-ttu-id="47675-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-170">REG_SZ</span></span> |  <span data-ttu-id="47675-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="47675-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="47675-172">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="47675-172">DSCP Value</span></span>       | <span data-ttu-id="47675-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-173">REG_SZ</span></span> |     <span data-ttu-id="47675-174">46</span><span class="sxs-lookup"><span data-stu-id="47675-174">46</span></span>      |
   |        <span data-ttu-id="47675-175">IP locale</span><span class="sxs-lookup"><span data-stu-id="47675-175">Local IP</span></span>        | <span data-ttu-id="47675-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="47675-177">Longueur du préfixe IP local</span><span class="sxs-lookup"><span data-stu-id="47675-177">Local IP Prefix Length</span></span> | <span data-ttu-id="47675-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="47675-179">Port local</span><span class="sxs-lookup"><span data-stu-id="47675-179">Local Port</span></span>       | <span data-ttu-id="47675-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-180">REG_SZ</span></span> | <span data-ttu-id="47675-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="47675-181">50000-50019</span></span> |
   |        <span data-ttu-id="47675-182">Protocole</span><span class="sxs-lookup"><span data-stu-id="47675-182">Protocol</span></span>        | <span data-ttu-id="47675-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="47675-184">Adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="47675-184">Remote IP</span></span>        | <span data-ttu-id="47675-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="47675-186">Préfixe d’adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="47675-186">Remote IP Prefix</span></span>    | <span data-ttu-id="47675-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="47675-188">Port distant</span><span class="sxs-lookup"><span data-stu-id="47675-188">Remote Port</span></span>       | <span data-ttu-id="47675-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="47675-190">Taux de limitation</span><span class="sxs-lookup"><span data-stu-id="47675-190">Throttle Rate</span></span>      | <span data-ttu-id="47675-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="47675-191">REG_SZ</span></span> |     <span data-ttu-id="47675-192">minute</span><span class="sxs-lookup"><span data-stu-id="47675-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="47675-193">Vérifiez que la valeur de l’entrée de nom d’application est correcte pour le client que vous utilisez et vérifiez que la valeur DSCP et les entrées de port local reflètent les paramètres de l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="47675-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="47675-194">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47675-194">Related topics</span></span>

[<span data-ttu-id="47675-195">Mise en œuvre de la qualité de service (QoS) dans teams</span><span class="sxs-lookup"><span data-stu-id="47675-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)