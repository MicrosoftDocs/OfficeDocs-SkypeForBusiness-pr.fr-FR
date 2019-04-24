---
title: Configuration des plages de ports et une stratégie de qualité de Service pour vos serveurs de conférence, d’Application et de médiation
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article explique comment configurer une stratégie de qualité de Service pour vos serveurs de conférence, d’Application et de médiation et les plages de ports.
ms.openlocfilehash: f1452c9166eb557d186b8569a37d5abb885d4354
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199558"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configuration des plages de ports et une stratégie de qualité de Service pour vos serveurs de conférence, d’Application et de médiation

Cet article explique comment configurer une stratégie de qualité de Service pour vos serveurs de conférence, d’Application et de médiation et les plages de ports.

## <a name="configure-port-ranges"></a>Configurer les plages de ports

Pour implémenter la qualité de Service, vous devez configurer les plages de ports identiques pour l’audio, vidéo, partage d’application et sur vos serveurs de conférence, d’Application et de médiation ; en outre, les plages de ports ne doivent pas se chevaucher en aucune façon. Pour utiliser un exemple simple, supposons que vous utilisez 10000 10999 par le biais de ports pour la vidéo sur vos serveurs de conférence. Cela signifie que vous devez réserver également les ports 10000 par le biais de 10999 vidéo sur vos serveurs d’applications et de médiation. Si vous le faites pas, QoS ne fonctionnera pas comme prévu.

De même, supposons que vous réservez ports 10000 par le biais de 10999 pour la vidéo, mais puis réserve ports 10500 par le biais de 11999 pour l’audio. Cela peut créer des problèmes de qualité de Service, car le port compris chevauchement. Des stratégies QoS, chaque modalité doit avoir un ensemble unique de ports : Si vous utilisez 10000 10999 par le biais de ports pour la vidéo, puis vous devrez utiliser une autre plage (par exemple, 11 000 par le biais de 11999, pour l’audio).

Par défaut, les plages de ports audio et vidéo ne se chevauchent pas dans Skype pour Business Server ; Toutefois, les plages de ports affectés au partage chevauchement avec à la fois les plages de ports audio et vidéo d’application. (Qui, à son tour, signifie qu’aucun de ces plages sont uniques). Vous pouvez vérifier les plages de ports existant pour vos serveurs de conférence, d’Application et de médiation en exécutant les trois commandes suivantes à partir de la Skype pour Business Server Management Shell :

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Comme vous pouvez le constater dans les commandes ci-dessus, deux valeurs de propriété distinct est affecté à chaque type de port audio, vidéo et partage d’application – : le port de début et le nombre de ports. Le port de début indique le premier port utilisé pour cette modalité ; par exemple, si le début du port audio est égal à 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000. Si le nombre de ports audio est 2 (qui n’est pas une valeur valide, mais est utilisé ici à des fins d’illustration), ce qui signifie que seuls deux ports sont alloués pour l’audio. Si le premier port est le port 50000 et il existe un total de deux ports, cela signifie que le second port doit être le port 50001 (port plages doivent être contigus). Par conséquent, la plage de ports audio serait ports 50000 par le biais de 50 001, inclus.<BR><br>Notez également que serveur d’applications et serveur de médiation ne prennent en charge QoS audio ; Il est inutile de modifier la vidéo ou les ports de vos serveurs d’applications ou les serveurs de médiation de partage d’application.

Si vous exécutez les trois commandes précédentes, vous verrez que le port par défaut des valeurs pour Skype pour Business Server configurés comme suit :

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriété</th>
<th>Serveur de conférence</th>
<th>Serveur d’applications</th>
<th>serveur de médiation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Comme mentionné précédemment, lors de la configuration Skype pour les ports Business Server pour la qualité de service, vous devez vous assurer que : 1) les paramètres de port audio sont identiques entre les vôtres, les serveurs de conférence, d’Application et de médiation ; et, 2) les plages de ports ne se chevauchent pas. Si vous examinez attentivement le tableau précédent, vous verrez que les plages de ports sont identiques entre les types de trois serveurs. Par exemple, le port audio initial est défini sur le port 49152 sur chaque type de serveur, et le nombre total de ports réservés pour l’audio de chaque serveur est également identique : 8348. Toutefois, le port plages chevauchement : ports audio démarrer au port 49152, mais donc font les ports attribuée au partage d’application. Afin de tirer le meilleur parti de la qualité de Service, partage d’application doit être reconfiguré pour utiliser une plage de port unique. Par exemple, vous pouvez configurer le partage d’application pour démarrer au port 40803 et utiliser des 8348 ports. (Pourquoi 8348 ports ? Si vous ajoutez ces valeurs--40803 + 8348--, cela signifie que le partage d’application utilise les ports 40803 via le port 49150. Étant donné que les ports audio ne commencent pas jusqu'à ce que le port 49152, vous n’aura plus un chevauchement des plages de ports.)

Une fois que vous avez sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez effectuer votre modification à l’aide de l’applet de commande Set-CsConferencingServer. Cette modification n’a pas besoin être effectuées sur vos serveurs d’applications ou sur vos serveurs de médiation, étant donné que ces serveurs ne traitent pas le trafic de partage d’application. Vous devez uniquement modifier les valeurs de port sur ces serveurs si vous décidez de réaffecter les ports utilisés pour le trafic audio.

Pour modifier les valeurs de ports partage d’application sur un seul serveur de conférence, exécutez une commande similaire à celle-ci à partir de la Skype pour Business Server Management Shell :

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si vous souhaitez apporter ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place :

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Après avoir modifié les paramètres de port, vous devez arrêter, puis redémarrez chaque service affecté par les modifications.

Il n’est pas obligatoire que vos serveurs de conférence, les serveurs d’applications et les serveurs de médiation partagent la même plage port exacte ; la spécification de la valeur true uniquement est que vous réservez plages de ports unique sur tous vos serveurs. Toutefois, l’administration sera généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurer une stratégie de qualité de Service dans Skype pour Business Server pour vos serveurs de conférence, d’Application et de médiation

Configuration des plages de ports facilite l’utilisation de la qualité de Service en s’assurant que tout le trafic d’un type spécifié (par exemple, tout le trafic audio) traverse le même ensemble de ports. Cela facilite le système identifier et marquer un paquet donné : si le port 49152 est réservé pour le trafic audio, puis les paquets envoyés via le port 49152 peuvent être marqués avec un code DSCP qui indique qu’il s’agit d’un paquet audio. Cela permet à son tour, routeurs d’identifier le paquet comme un paquet audio et lui donner la priorité plus élevée que les paquets désactivées (tels que les paquets permet de copier un fichier d’un serveur vers un autre).

Toutefois, la restriction simplement un ensemble de ports à un type spécifique de trafic n’entraîne pas de paquets transmis par le biais de ces ports est marqués avec le code DSCP approprié. Outre la définition de plages de ports, vous devez également créer des stratégies de qualité de Service qui spécifient le code DSCP à associer à chaque plage de ports. Pour Skype pour Business Server, cela signifie généralement la création de deux stratégies : un pour l’audio et l’autre pour la vidéo.

Qualité de Service les stratégies sont plus simple à créer et à gérer, à l’aide de la stratégie de groupe. (Ces mêmes stratégies peuvent également être créées à l’aide de stratégies de sécurité locale. Toutefois, qui requiert vous permettent de répéter la même procédure sur chaque ordinateur.) Votre ensemble initial des stratégies QoS (un pour l’audio) et un pour la vidéo doit être appliquée uniquement aux Skype pour les ordinateurs Business Server exécutant le serveur de conférence, serveur d’applications et/ou services du serveur de médiation. Si tous ces ordinateurs se trouvent dans l’unité d’organisation Active Directory même, vous pouvez simplement assigner le nouvel objet de stratégie de groupe (GPO) à cette unité d’organisation. Sinon, vous pouvez effectuer les autres étapes de la cible de la nouvelle stratégie sur les ordinateurs spécifiés ; par exemple, vous pouvez placer les ordinateurs appropriés dans un groupe de sécurité, puis utiliser le filtrage de sécurité de stratégie de groupe pour appliquer la stratégie de groupe uniquement à ce groupe de sécurité.

Pour créer une stratégie de qualité de Service pour gérer les paramètres audio, ouvrez une session un ordinateur où la gestion des stratégies de groupe a été installée. Ouvrez Gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestion des stratégies de groupe**) et puis procédez comme suit :

1.  Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée. Par exemple, si tous vos Skype pour les ordinateurs Business Server se trouvent dans une unité d’organisation nommée Skype pour Business Server, puis la nouvelle stratégie doit être créée en la Skype pour l’unité d’organisation du serveur Business.

2.  Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.

3.  Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Skype pour Business Server QoS**), puis cliquez sur **OK**.

4.  Avec le bouton droit de la stratégie créée, puis cliquez sur **Modifier**.

5.  Dans l’éditeur de gestion de stratégie de groupe, développez **Configuration ordinateur**, développez **stratégies**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie (par exemple, **Skype pour Business Server QoS**) dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**. Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.

7.  Dans la page suivante, vérifiez que **toutes les applications** est sélectionné, puis cliquez sur **suivant**. Il vérifie simplement que toutes les applications corresponde aux paquets à partir de la plage de ports spécifié par le code DSCP spécifié.

8.  Dans la troisième page, assurez-vous **toute adresse IP source et l’adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**. Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.

9.  Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau plus couramment utilisés par Skype pour Business Server et ses applications clientes.

10. Sous le titre, **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port source ou de la plage**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservé ports 49152 par le biais de ports 57500 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **49152:57500**. Cliquez sur **Terminer**.

> [!NOTE]  
> La valeur DSCP 46 est quelque peu arbitraire : bien que le marquage DSCP 46 est souvent utilisé pour le marquage des paquets audio, il est inutile d’utiliser le marquage DSCP 46 pour les communications audio. Si vous avez déjà implémenté QoS et que vous utilisez un autre code DSCP pour l’audio (par exemple, le marquage DSCP 40), vous devez configurer votre stratégie de qualité de Service pour utiliser ce même code (autrement dit, 40 pour l’audio). Si vous implémentez uniquement maintenant la qualité de Service, puis il est recommandé d’utiliser simplement de DSCP 46 pour l’audio, car cette valeur est couramment utilisée pour marquer les paquets audio.

Une fois que vous avez créé la stratégie QoS pour le trafic audio, vous devez ensuite créer une deuxième stratégie pour le trafic vidéo (et, éventuellement, une troisième stratégie pour gérer le trafic de partage d’application). Pour créer une stratégie pour la vidéo, suivez la même procédure de base que vous avez suivi lors de la création de la stratégie audio, effectuant les substitutions :

  - Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour Business Server vidéo**).

  - Définissez la valeur DSCP **34** au lieu de 46. (Notez que vous n’avez pas d’utiliser une valeur DSCP de 34. La seule exigence est que vous utilisez une autre valeur DSCP pour la vidéo que vous avez utilisé pour l’audio.)

  - Utiliser la plage de ports précédemment configuré pour le trafic vidéo. Par exemple, si vous avez réservé ports 57501 et 65 535 pour la vidéo, définissez la plage de ports à ceci : **57501:65535**.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :

  - Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour le partage d’Application Business Server**).

  - Définissez la valeur DSCP à **24** au lieu de 46. (Là encore, il est inutile d’utiliser une valeur DSCP sur 24. La seule exigence est que vous utilisez une autre valeur DSCP pour le partage d’application que vous avez utilisé pour l’audio ou vidéo.)

  - Utiliser la plage de ports précédemment configuré pour le trafic vidéo. Par exemple, si vous avez réservé ports 40803 via et 49 151 partage d’application, définissez la plage de ports à ceci : **40803:49151**.

Les nouvelles stratégies que vous avez créé ne prendra pas effet jusqu'à ce que la stratégie de groupe a été actualisée sur votre Skype pour les ordinateurs serveurs d’entreprise. Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur où la stratégie de groupe doivent être actualisées :

    Gpupdate.exe /force

Cette commande peut être exécutée à partir de dans la Skype pour Business Server Management Shell ou à partir de n’importe quelle fenêtre de commande s’exécutant sous les informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez sur **invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

Pour vérifier que les nouvelles stratégies QoS ont été appliquées, procédez comme suit :

1.  Sur un Skype pour ordinateur Business Server, cliquez sur **Démarrer**, puis cliquez sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.

3.  Dans l’Éditeur du Registre, développez **l’ordinateur**, **HKEY\_LOCAL\_ordinateur**, développez **SOFTWARE**, développez **stratégies**, développez **Microsoft**, développez **Windows**, puis cliquez sur **QoS**. Sous **QoS** , vous devez voir des clés de Registre pour chacune des stratégies QoS que vous venez de créer. Par exemple, si vous avez créé deux nouvelles stratégies (un nommé Skype pour Business Server Audio QoS) et l’autres Skype nommé Business Server vidéo QoS, vous devez voir entrées de Registre pour Skype pour Business Server Audio QoS et Skype Business Server vidéo QoS.

Pour garantir que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en procédant comme suit :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_ordinateur**, développez **système**, développez **CurrentControlSet**, développez **services**et **puis TCPIP**.

4.  Cliquez sur **TCP/IP**, pointez sur **Nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre est créée, tapez **QoS**, puis appuyez sur ENTRÉE pour renommer la clé.

5.  Avec le bouton droit **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**. Une fois la nouvelle valeur de Registre est créée, tapez **n’utilisez pas l’authentification réseau**, puis appuyez sur ENTRÉE pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser l’authentification réseau**. Dans la boîte de dialogue **Modification de la chaîne** , tapez **1** dans la zone **valeur** , puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et redémarrez votre ordinateur.
