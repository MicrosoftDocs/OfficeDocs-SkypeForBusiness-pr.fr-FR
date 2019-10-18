---
title: Implémenter la qualité de service dans Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implémenter la qualité de service (QoS) pour les clients Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28e6664fa43819493e5b9e02d182bcec44f00905
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572562"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="afcd7-103">Définir la qualité de service sur les clients Windows</span><span class="sxs-lookup"><span data-stu-id="afcd7-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="afcd7-104">Vous pouvez utiliser la QoS basée sur une stratégie dans une stratégie de groupe pour définir la plage de ports sources pour la valeur DSCP prédéfinie dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="afcd7-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="afcd7-105">Les plages de port spécifiées dans le tableau suivant constituent un point de départ pour créer une stratégie pour chaque charge de travail.</span><span class="sxs-lookup"><span data-stu-id="afcd7-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="afcd7-106">_Plages de port initiales recommandées_</span><span class="sxs-lookup"><span data-stu-id="afcd7-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="afcd7-107">Type de trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="afcd7-107">Media traffic type</span></span>| <span data-ttu-id="afcd7-108">Plage de ports sources du client</span><span class="sxs-lookup"><span data-stu-id="afcd7-108">Client source port range</span></span> |<span data-ttu-id="afcd7-109">Protocole</span><span class="sxs-lookup"><span data-stu-id="afcd7-109">Protocol</span></span>|<span data-ttu-id="afcd7-110">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="afcd7-110">DSCP value</span></span>|<span data-ttu-id="afcd7-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="afcd7-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="afcd7-112">Audio</span><span class="sxs-lookup"><span data-stu-id="afcd7-112">Audio</span></span>| <span data-ttu-id="afcd7-113">50000 – 50019</span><span class="sxs-lookup"><span data-stu-id="afcd7-113">50,000–50,019</span></span>|<span data-ttu-id="afcd7-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="afcd7-114">TCP/UDP</span></span>|<span data-ttu-id="afcd7-115">46</span><span class="sxs-lookup"><span data-stu-id="afcd7-115">46</span></span>|<span data-ttu-id="afcd7-116">Acheminement accéléré (EF)</span><span class="sxs-lookup"><span data-stu-id="afcd7-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="afcd7-117">Vidéo</span><span class="sxs-lookup"><span data-stu-id="afcd7-117">Video</span></span>| <span data-ttu-id="afcd7-118">50,020 – 50039</span><span class="sxs-lookup"><span data-stu-id="afcd7-118">50,020–50,039</span></span>|<span data-ttu-id="afcd7-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="afcd7-119">TCP/UDP</span></span>|<span data-ttu-id="afcd7-120">34</span><span class="sxs-lookup"><span data-stu-id="afcd7-120">34</span></span>|<span data-ttu-id="afcd7-121">Acheminement assuré (AF41)</span><span class="sxs-lookup"><span data-stu-id="afcd7-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="afcd7-122">Partage d’écran ou d’application</span><span class="sxs-lookup"><span data-stu-id="afcd7-122">Application/Screen Sharing</span></span>| <span data-ttu-id="afcd7-123">50,040 – 50059</span><span class="sxs-lookup"><span data-stu-id="afcd7-123">50,040–50,059</span></span>|<span data-ttu-id="afcd7-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="afcd7-124">TCP/UDP</span></span>|<span data-ttu-id="afcd7-125">19</span><span class="sxs-lookup"><span data-stu-id="afcd7-125">18</span></span>|<span data-ttu-id="afcd7-126">Transfert assuré (AF21)</span><span class="sxs-lookup"><span data-stu-id="afcd7-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="afcd7-127">Dans la mesure du possible, vous pouvez configurer les paramètres de QoS basée sur une stratégie au sein d’un objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="afcd7-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="afcd7-128">Les étapes suivantes sont similaires à la [configuration de plages de ports et d’une politique de qualité de service pour vos clients sur Skype entreprise Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui comporte des informations supplémentaires qui peuvent ne pas être nécessaires.</span><span class="sxs-lookup"><span data-stu-id="afcd7-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="afcd7-129">Pour créer une stratégie audio QoS pour des ordinateurs Windows 10 liés à un domaine, vous devez d’abord vous connecter à un ordinateur sur lequel est installée la gestion des stratégies de groupe.</span><span class="sxs-lookup"><span data-stu-id="afcd7-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="afcd7-130">Ouvrez gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur outils d’administration, cliquez sur gestion des stratégies de groupe), puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="afcd7-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="afcd7-131">Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="afcd7-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="afcd7-132">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **clients**, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.</span><span class="sxs-lookup"><span data-stu-id="afcd7-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="afcd7-133">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="afcd7-134">Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="afcd7-135">Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="afcd7-136">Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="afcd7-137">Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="afcd7-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="afcd7-138">Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="afcd7-139">Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="afcd7-140">Sur la page suivante, sélectionnez **uniquement les applications avec ce nom d’exécutable** et entrez le nom **Teams. exe**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="afcd7-141">Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant du client Teams.</span><span class="sxs-lookup"><span data-stu-id="afcd7-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="afcd7-142">Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="afcd7-143">Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé les paquets et de l’ordinateur (adresse IP) recevant les paquets.</span><span class="sxs-lookup"><span data-stu-id="afcd7-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="afcd7-144">Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** .</span><span class="sxs-lookup"><span data-stu-id="afcd7-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="afcd7-145">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés.</span><span class="sxs-lookup"><span data-stu-id="afcd7-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="afcd7-146">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="afcd7-147">Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="afcd7-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="afcd7-148">Par exemple, si vous avez réservé ports 50000 via ports 50019 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="afcd7-149">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="afcd7-149">Click **Finish**.</span></span>

11. <span data-ttu-id="afcd7-150">Répétez les étapes 5-10 pour créer des stratégies pour la vidéo et le partage de bureau et d’application</span><span class="sxs-lookup"><span data-stu-id="afcd7-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="afcd7-151">Les nouvelles stratégies que vous avez créées ne prennent effet qu’après la réactualisation de la stratégie de groupe sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="afcd7-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="afcd7-152">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="afcd7-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="afcd7-153">Sur chaque ordinateur sur lequel vous souhaitez actualiser une stratégie de groupe, ouvrez une console de commandes.</span><span class="sxs-lookup"><span data-stu-id="afcd7-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="afcd7-154">Vérifiez que la console de commandes est définie sur Exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="afcd7-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="afcd7-155">À l’invite de commandes, entrez</span><span class="sxs-lookup"><span data-stu-id="afcd7-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="afcd7-156">Vérifier les marquages DSCP dans l’objet de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="afcd7-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="afcd7-157">Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="afcd7-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="afcd7-158">Ouvrez une console de commandes.</span><span class="sxs-lookup"><span data-stu-id="afcd7-158">Open a command console.</span></span> <span data-ttu-id="afcd7-159">Vérifiez que la console de commandes est définie sur Exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="afcd7-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="afcd7-160">À l’invite de commandes, entrez :</span><span class="sxs-lookup"><span data-stu-id="afcd7-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="afcd7-161">Cette opération génère un rapport et l’envoie à un fichier texte nommé GP. txt.</span><span class="sxs-lookup"><span data-stu-id="afcd7-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="afcd7-162">Vous pouvez également entrer la commande suivante pour générer les mêmes données dans un rapport HTML plus lisible nommé GP. html :</span><span class="sxs-lookup"><span data-stu-id="afcd7-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="afcd7-163">![Capture d’écran de la fenêtre de console exécutant la commande Gpresult.](media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console exécutant la commande Gpresult.")</span><span class="sxs-lookup"><span data-stu-id="afcd7-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="afcd7-164">Dans le fichier généré, recherchez le titre **appliqué objets de stratégie de groupe** , puis vérifiez que les noms des objets de stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.</span><span class="sxs-lookup"><span data-stu-id="afcd7-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="afcd7-165">Ouvrez l’éditeur du Registre et rendez-vous sur :</span><span class="sxs-lookup"><span data-stu-id="afcd7-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="afcd7-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="afcd7-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="afcd7-167">Vérifiez les valeurs des entrées de registre indiquées dans le tableau 4.</span><span class="sxs-lookup"><span data-stu-id="afcd7-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="afcd7-168">_Tableau 4. Valeurs pour les entrées de Registre Windows pour QoS_</span><span class="sxs-lookup"><span data-stu-id="afcd7-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="afcd7-169">Nom</span><span class="sxs-lookup"><span data-stu-id="afcd7-169">Name</span></span>          |  <span data-ttu-id="afcd7-170">Type</span><span class="sxs-lookup"><span data-stu-id="afcd7-170">Type</span></span>  |    <span data-ttu-id="afcd7-171">Données</span><span class="sxs-lookup"><span data-stu-id="afcd7-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="afcd7-172">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="afcd7-172">Application Name</span></span>    | <span data-ttu-id="afcd7-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-173">REG_SZ</span></span> |  <span data-ttu-id="afcd7-174">Teams. exe</span><span class="sxs-lookup"><span data-stu-id="afcd7-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="afcd7-175">Valeur DSCP</span><span class="sxs-lookup"><span data-stu-id="afcd7-175">DSCP Value</span></span>       | <span data-ttu-id="afcd7-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-176">REG_SZ</span></span> |     <span data-ttu-id="afcd7-177">46</span><span class="sxs-lookup"><span data-stu-id="afcd7-177">46</span></span>      |
   |        <span data-ttu-id="afcd7-178">IP locale</span><span class="sxs-lookup"><span data-stu-id="afcd7-178">Local IP</span></span>        | <span data-ttu-id="afcd7-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="afcd7-180">Longueur du préfixe IP local</span><span class="sxs-lookup"><span data-stu-id="afcd7-180">Local IP Prefix Length</span></span> | <span data-ttu-id="afcd7-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="afcd7-182">Port local</span><span class="sxs-lookup"><span data-stu-id="afcd7-182">Local Port</span></span>       | <span data-ttu-id="afcd7-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-183">REG_SZ</span></span> | <span data-ttu-id="afcd7-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="afcd7-184">50000-50019</span></span> |
   |        <span data-ttu-id="afcd7-185">Protocole</span><span class="sxs-lookup"><span data-stu-id="afcd7-185">Protocol</span></span>        | <span data-ttu-id="afcd7-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="afcd7-187">Adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="afcd7-187">Remote IP</span></span>        | <span data-ttu-id="afcd7-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="afcd7-189">Préfixe d’adresse IP distante</span><span class="sxs-lookup"><span data-stu-id="afcd7-189">Remote IP Prefix</span></span>    | <span data-ttu-id="afcd7-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="afcd7-191">Port distant</span><span class="sxs-lookup"><span data-stu-id="afcd7-191">Remote Port</span></span>       | <span data-ttu-id="afcd7-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="afcd7-193">Taux de limitation</span><span class="sxs-lookup"><span data-stu-id="afcd7-193">Throttle Rate</span></span>      | <span data-ttu-id="afcd7-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="afcd7-194">REG_SZ</span></span> |     <span data-ttu-id="afcd7-195">minute</span><span class="sxs-lookup"><span data-stu-id="afcd7-195">-1</span></span>      |

5. <span data-ttu-id="afcd7-196">Vérifiez que la valeur de l’entrée de nom d’application est correcte pour le client que vous utilisez et vérifiez que la valeur DSCP et les entrées de port local reflètent les paramètres de l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="afcd7-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
