---
title: Implémenter la qualité de service dans Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Implémentez la qualité de Service (QoS) pour les clients Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1f80ede0432c3666a1974b1e0c8d7fa3dc2bbfc
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408266"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="6761c-103">Jeu de QoS sur les clients Windows</span><span class="sxs-lookup"><span data-stu-id="6761c-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="6761c-104">Vous pouvez utiliser QoS basée sur les stratégies au sein de la stratégie de groupe pour définir la plage de ports source pour la valeur DSCP prédéfinie dans le client d’équipes.</span><span class="sxs-lookup"><span data-stu-id="6761c-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="6761c-105">Les plages de ports spécifiés dans le tableau suivant sont un point de départ pour créer une stratégie pour chaque charge de travail.</span><span class="sxs-lookup"><span data-stu-id="6761c-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="6761c-106">_Recommandé de plages de ports initiale_</span><span class="sxs-lookup"><span data-stu-id="6761c-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="6761c-107">Type de trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="6761c-107">Media traffic type</span></span>| <span data-ttu-id="6761c-108">Plage de ports client source</span><span class="sxs-lookup"><span data-stu-id="6761c-108">Client source port range</span></span> |<span data-ttu-id="6761c-109">Protocole</span><span class="sxs-lookup"><span data-stu-id="6761c-109">Protocol</span></span>|<span data-ttu-id="6761c-110">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="6761c-110">DSCP value</span></span>|<span data-ttu-id="6761c-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="6761c-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="6761c-112">Audio</span><span class="sxs-lookup"><span data-stu-id="6761c-112">Audio</span></span>| <span data-ttu-id="6761c-113">50 000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="6761c-113">50,000–50,019</span></span>|<span data-ttu-id="6761c-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6761c-114">TCP/UDP</span></span>|<span data-ttu-id="6761c-115">46</span><span class="sxs-lookup"><span data-stu-id="6761c-115">46</span></span>|<span data-ttu-id="6761c-116">Acheminement accéléré (EF)</span><span class="sxs-lookup"><span data-stu-id="6761c-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="6761c-117">Vidéo</span><span class="sxs-lookup"><span data-stu-id="6761c-117">Video</span></span>| <span data-ttu-id="6761c-118">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="6761c-118">50,020–50,039</span></span>|<span data-ttu-id="6761c-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6761c-119">TCP/UDP</span></span>|<span data-ttu-id="6761c-120">34</span><span class="sxs-lookup"><span data-stu-id="6761c-120">34</span></span>|<span data-ttu-id="6761c-121">Acheminement assuré (AF41)</span><span class="sxs-lookup"><span data-stu-id="6761c-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="6761c-122">Partage d’application/écran</span><span class="sxs-lookup"><span data-stu-id="6761c-122">Application/Screen Sharing</span></span>| <span data-ttu-id="6761c-123">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="6761c-123">50,040–50,059</span></span>|<span data-ttu-id="6761c-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6761c-124">TCP/UDP</span></span>|<span data-ttu-id="6761c-125">18</span><span class="sxs-lookup"><span data-stu-id="6761c-125">18</span></span>|<span data-ttu-id="6761c-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="6761c-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="6761c-127">Dans la mesure du possible, configurez les paramètres de QoS basée sur la stratégie au sein d’un objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="6761c-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="6761c-128">Les étapes suivantes sont très similaires à la [Configuration des plages de ports et une stratégie de qualité de Service pour vos clients sur Skype pour Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui comprend des informations supplémentaires qui ne peuvent pas être nécessaires.</span><span class="sxs-lookup"><span data-stu-id="6761c-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="6761c-129">Pour créer une stratégie audio QoS pour les ordinateurs Windows 10 AccountManagement liés, ouvrez une session un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="6761c-129">To create a QoS audio policy for domian-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="6761c-130">Ouvrez Gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur Outils d’administration, puis cliquez sur gestion des stratégies de groupe), puis suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6761c-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="6761c-131">Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="6761c-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="6761c-132">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **Clients**, la nouvelle stratégie doit être créée en l’unité d’organisation du Client.</span><span class="sxs-lookup"><span data-stu-id="6761c-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="6761c-133">Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.</span><span class="sxs-lookup"><span data-stu-id="6761c-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="6761c-134">Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6761c-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="6761c-135">Avec le bouton droit de la stratégie nouvellement créée, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6761c-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="6761c-136">Dans l’éditeur de gestion de stratégie de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="6761c-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="6761c-137">Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="6761c-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="6761c-138">Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**.</span><span class="sxs-lookup"><span data-stu-id="6761c-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="6761c-139">Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6761c-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="6761c-140">Dans la page suivante, sélectionnez **uniquement les applications portant ce nom exécutable** et entrez le nom **Teams.exe**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6761c-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="6761c-141">Ce paramètre indique à la stratégie pour définir la priorité uniquement le trafic correspondant à partir du client équipes.</span><span class="sxs-lookup"><span data-stu-id="6761c-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="6761c-142">Dans la troisième page, assurez-vous que **toute adresse IP source** et **n’importe quelle adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6761c-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="6761c-143">Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.</span><span class="sxs-lookup"><span data-stu-id="6761c-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="6761c-144">Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** .</span><span class="sxs-lookup"><span data-stu-id="6761c-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="6761c-145">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisées.</span><span class="sxs-lookup"><span data-stu-id="6761c-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="6761c-146">Sous le titre, **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port source ou de la plage**.</span><span class="sxs-lookup"><span data-stu-id="6761c-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="6761c-147">Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="6761c-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="6761c-148">Par exemple, si vous réservé ports 50000 par le biais de ports 50019 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="6761c-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="6761c-149">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6761c-149">Click **Finish**.</span></span>

11. <span data-ttu-id="6761c-150">Répétez les étapes 5 à 10 pour créer des stratégies pour la vidéo et l’Application/partage du bureau, en remplaçant les valeurs appropriées dans les étapes 6 et 10.</span><span class="sxs-lookup"><span data-stu-id="6761c-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="6761c-151">Les nouvelles stratégies que vous avez créé ne prennent effet tant que la stratégie de groupe a été actualisée sur vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="6761c-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="6761c-152">Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="6761c-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="6761c-153">Sur chaque ordinateur pour lequel vous voulez actualiser la stratégie de groupe, ouvrez une console de commande.</span><span class="sxs-lookup"><span data-stu-id="6761c-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="6761c-154">Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6761c-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="6761c-155">À l’invite de commandes, entrez</span><span class="sxs-lookup"><span data-stu-id="6761c-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="6761c-156">Vérifier le marquage DSCP dans l’objet de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="6761c-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="6761c-157">Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6761c-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="6761c-158">Ouvrez une console de commande.</span><span class="sxs-lookup"><span data-stu-id="6761c-158">Open a command console.</span></span> <span data-ttu-id="6761c-159">Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6761c-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="6761c-160">À l’invite de commandes, entrez :</span><span class="sxs-lookup"><span data-stu-id="6761c-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="6761c-161">Cela générer un rapport et envoyez-le à un fichier texte nommé gp.txt.</span><span class="sxs-lookup"><span data-stu-id="6761c-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="6761c-162">Vous pouvez également entrer la commande suivante pour produire les mêmes données dans un rapport HTML plus lisible nommé gp.html :</span><span class="sxs-lookup"><span data-stu-id="6761c-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="6761c-163">![Capture d’écran de la fenêtre de console exécutant la commande gpresult.] (media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console exécutant la commande gpresult.")</span><span class="sxs-lookup"><span data-stu-id="6761c-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="6761c-164">Dans le fichier généré, recherchez l’en-tête **Appliqué des objets de stratégie de groupe** et vérifiez que les noms des objets de stratégie de groupe créés précédemment sont dans la liste des stratégies appliquées.</span><span class="sxs-lookup"><span data-stu-id="6761c-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="6761c-165">Ouvrez l’Éditeur du Registre et accédez à :</span><span class="sxs-lookup"><span data-stu-id="6761c-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="6761c-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="6761c-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="6761c-167">Vérifiez les valeurs pour les entrées de Registre répertoriées dans le tableau 4.</span><span class="sxs-lookup"><span data-stu-id="6761c-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="6761c-168">_Le tableau 4. Valeurs des entrées du Registre Windows pour QoS_</span><span class="sxs-lookup"><span data-stu-id="6761c-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="6761c-169">Nom</span><span class="sxs-lookup"><span data-stu-id="6761c-169">Name</span></span>          |  <span data-ttu-id="6761c-170">Type</span><span class="sxs-lookup"><span data-stu-id="6761c-170">Type</span></span>  |    <span data-ttu-id="6761c-171">Données</span><span class="sxs-lookup"><span data-stu-id="6761c-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="6761c-172">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="6761c-172">Application Name</span></span>    | <span data-ttu-id="6761c-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-173">REG_SZ</span></span> |  <span data-ttu-id="6761c-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="6761c-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="6761c-175">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="6761c-175">DSCP Value</span></span>       | <span data-ttu-id="6761c-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-176">REG_SZ</span></span> |     <span data-ttu-id="6761c-177">46</span><span class="sxs-lookup"><span data-stu-id="6761c-177">46</span></span>      |
   |        <span data-ttu-id="6761c-178">Adresse IP locale</span><span class="sxs-lookup"><span data-stu-id="6761c-178">Local IP</span></span>        | <span data-ttu-id="6761c-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="6761c-180">Longueur du préfixe de l’adresse IP locale</span><span class="sxs-lookup"><span data-stu-id="6761c-180">Local IP Prefix Length</span></span> | <span data-ttu-id="6761c-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="6761c-182">Port local</span><span class="sxs-lookup"><span data-stu-id="6761c-182">Local Port</span></span>       | <span data-ttu-id="6761c-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-183">REG_SZ</span></span> | <span data-ttu-id="6761c-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="6761c-184">50000-50019</span></span> |
   |        <span data-ttu-id="6761c-185">Protocole</span><span class="sxs-lookup"><span data-stu-id="6761c-185">Protocol</span></span>        | <span data-ttu-id="6761c-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="6761c-187">Adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="6761c-187">Remote IP</span></span>        | <span data-ttu-id="6761c-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="6761c-189">Préfixe de l’adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="6761c-189">Remote IP Prefix</span></span>    | <span data-ttu-id="6761c-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="6761c-191">Port distant</span><span class="sxs-lookup"><span data-stu-id="6761c-191">Remote Port</span></span>       | <span data-ttu-id="6761c-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="6761c-193">Taux d’accélération</span><span class="sxs-lookup"><span data-stu-id="6761c-193">Throttle Rate</span></span>      | <span data-ttu-id="6761c-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6761c-194">REG_SZ</span></span> |     <span data-ttu-id="6761c-195">-1</span><span class="sxs-lookup"><span data-stu-id="6761c-195">-1</span></span>      |

5. <span data-ttu-id="6761c-196">Vérifiez que la valeur de l’entrée de nom de l’Application est correcte pour le client que vous utilisez, puis vérifiez que la valeur DSCP et le Port Local entrées reflètent les paramètres de l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="6761c-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
