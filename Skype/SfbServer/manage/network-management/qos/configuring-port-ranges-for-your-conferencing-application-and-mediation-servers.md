---
title: Configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article décrit la configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation.
ms.openlocfilehash: e0bd6092792a9ed813aadecc004f58830bc5b133
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279460"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation

Cet article décrit la configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation.

## <a name="configure-port-ranges"></a>Configurer des plages de ports

Pour implémenter la qualité de service, vous devez configurer des plages de port identiques pour le partage audio, vidéo et d’application sur vos serveurs de conférence, d’application et de médiation. de plus, ces plages de port ne doivent pas se chevaucher de quelque manière que ce soit. Par exemple, vous pouvez utiliser les ports 10000 à 10999 pour la vidéo sur vos serveurs de conférence. Cela signifie que vous devez également réserver les ports 10000 à 10999 pour la vidéo sur vos serveurs d’application et de médiation. Si ce n’est pas le cas, QoS ne fonctionnera pas comme prévu.

De même, supposons que vous réservez les ports 10000 à 10999 pour la vidéo, mais que vous réservez les ports 10500 à 11999 pour le son. Cela peut générer des problèmes de qualité de service, car les plages de port se chevauchent. Avec la qualité de service (QoS), chaque modalité doit avoir un ensemble unique de ports: Si vous utilisez les ports 10000 à 10999 pour la vidéo, vous devez utiliser une autre plage (par exemple, 11000 à 11999, pour le son).

Par défaut, les plages de ports audio et vidéo ne se chevauchent pas dans Skype entreprise Server. Toutefois, les plages de port affectées au partage d’application s’empiètent sur les plages de ports audio et vidéo. (Qui, à son tour, signifie qu’aucune de ces plages n’est unique.) Vous pouvez vérifier les plages de port existantes pour vos serveurs de conférences, d’applications et de médiation en exécutant les trois commandes suivantes dans Skype entreprise Server Management Shell:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Comme vous pouvez le voir dans les commandes précédentes, chaque type de port (audio, vidéo et partage d’application) assigne deux valeurs de propriété distinctes: le début du port et le nombre de ports. Le début du port indique le premier port utilisé pour cette modalité; par exemple, si le port audio démarre est égal à 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000. Si le nombre de ports audio est 2 (qui n’est pas une valeur valide, mais qui est utilisé ici à des fins d’illustration), cela signifie que deux ports sont attribués pour l’audio. Si le premier port est port 50000 et qu’il existe au total deux ports, cela signifie que le second port doit être le port 50001 (les plages de port doivent être contiguës). Par conséquent, la plage de port pour le son correspond aux ports 50000 à 50001 inclus.<BR><br>Notez également que le serveur d’applications et le serveur de médiation ne prennent pas en charge la QoS pour le son. vous n’avez pas besoin de changer les ports vidéo ou de partage d’application dans vos serveurs d’applications ou serveurs de médiation.

Si vous exécutez les trois commandes précédentes, vous constatez que les valeurs de port par défaut de Skype entreprise Server sont configurées comme suit:

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

Comme indiqué précédemment, lorsque vous configurez des ports de Skype entreprise Server pour la qualité de service (QoS), vous devez vous assurer que: 1 et 2) les plages de port ne se chevauchent pas. Si vous examinez de près le tableau précédent, vous verrez que les plages de port sont identiques entre les trois types de serveurs. Par exemple, le port audio de début est défini sur le port 49152 sur chaque type de serveur et le nombre total de ports réservés pour le son dans chaque serveur est également identique: 8348. Toutefois, le chevauchement des plages de port: les ports audio commencent au port 49152, mais les ports sont-ils mis de côté pour le partage d’application. Pour optimiser l’utilisation de la qualité du service, le partage d’application doit être reconfiguré pour utiliser une plage de ports unique. Par exemple, vous pouvez configurer le partage d’application pour qu’il commence au port 40803 et utilise les ports 8348. (Pourquoi 8348 ports? Si vous ajoutez ces valeurs ensemble--40803 + 8348, cela signifie que le partage d’application utilisera les ports 40803 via le port 49150. Étant donné que les ports audio ne commencent pas jusqu’au port 49152, il n’y a plus de plages de ports qui se chevauchent.)

Après avoir sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez apporter votre modification à l’aide de l’applet de passe Set-CsConferencingServer. Il n’est pas nécessaire de procéder à cette modification sur les serveurs d’applications ou sur les serveurs de médiation, car ces serveurs ne gèrent pas le trafic de partage d’application. Vous ne devez modifier les valeurs de port sur ces serveurs que si vous décidez de réaffecter les ports utilisés pour le trafic audio.

Pour modifier les valeurs de port du partage d’application sur un serveur de conférence unique, exécutez une commande similaire à celle-ci dans Skype entreprise Server Management Shell:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si vous voulez apporter ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Après avoir modifié les paramètres de port, vous devez arrêter, puis redémarrer chaque service affecté par ces changements.

Il n’est pas obligatoire que vos serveurs de conférence, serveurs d’applications et serveurs de médiation partagent exactement la même plage de port; la seule exigence requise est que vous réservez des plages de port uniques sur tous vos serveurs. Toutefois, l’administration sera généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurer une stratégie de qualité de service dans Skype entreprise Server pour vos serveurs de conférence, d’application et de médiation

La configuration de plages de ports facilite l’utilisation de la qualité de service en s’assurant que tout le trafic d’un type spécifique (par exemple, tout le trafic audio) est acheminé par le même ensemble de ports. Ainsi, le système peut facilement identifier et marquer un paquet donné: si le port 49152 est réservé au trafic audio, tout paquet transmis via le port 49152 peut être marqué avec un code DSCP indiquant qu’il s’agit d’un paquet audio. Cela permet aux routeurs d’identifier le paquet en tant que paquet audio et de lui attribuer une priorité plus élevée que les paquets non marqués (par exemple, les paquets utilisés pour copier un fichier d’un serveur vers un autre).

En revanche, le simple fait de limiter un ensemble de ports à un type spécifique de trafic n’entraîne pas le passage de paquets avec le code DSCP approprié. En plus de définir des plages de port, vous devez également créer des stratégies de qualité de service qui spécifient le code DSCP à associer à chaque plage de ports. Pour Skype entreprise Server, il s’agit généralement de créer deux stratégies: une pour le son et une pour la vidéo.

Les stratégies de qualité de service sont le plus facile à créer et à gérer via une stratégie de groupe. (Ces mêmes stratégies peuvent également être créées à l’aide de stratégies de sécurité locales. Toutefois, vous devez répéter la même procédure sur chacun d’eux et sur tous les ordinateurs.) Votre ensemble initial de stratégies de QoS (une pour le son et l’autre pour la vidéo) ne doit être appliqué qu’aux ordinateurs Skype entreprise Server exécutant le serveur de conférence, le serveur d’applications et/ou les services de médiation. Si tous ces ordinateurs sont situés dans la même UO Active Directory, vous pouvez simplement affecter le nouvel objet de stratégie de groupe à cette unité d’organisation. Vous pouvez également effectuer d’autres opérations pour cibler la nouvelle stratégie sur les ordinateurs spécifiques. par exemple, vous pouvez placer les ordinateurs appropriés dans un groupe de sécurité, puis utiliser le filtrage de la sécurité de la stratégie de groupe pour appliquer l’objet de stratégie de groupe à ce groupe de sécurité.

Pour créer une stratégie de qualité de service pour la gestion du son, connectez-vous à un ordinateur sur lequel est installée la gestion des stratégies de groupe. Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit:

1.  Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs Skype entreprise Server résident dans une unité d’organisation nommée Skype entreprise Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Skype entreprise Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , tapez le nom du nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Skype entreprise Server QoS**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

5.  Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **stratégies**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée** sur une stratégie, dans la page ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **Skype entreprise Server QoS**) dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

7.  Dans la page suivante, assurez-vous que l’option **toutes les applications** est sélectionnée, puis cliquez sur **suivant**. Cela permet de s’assurer que toutes les applications correspondent aux paquets de la plage de ports spécifiée avec le code DSCP spécifié.

8.  Sur la troisième page, assurez-vous que toutes les **adresses IP source et adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.

9.  Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Skype entreprise Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 49152 via ports 57500 pour le trafic audio, entrez la plage de ports à l’aide du format suivant: **49152:57500**. Cliquez sur **Terminer**.

> [!NOTE]  
> La valeur DSCP de 46 est légèrement arbitraire: bien que le DSCP 46 soit souvent utilisé pour marquer les paquets audio, vous ne devez pas utiliser DSCP 46 pour les communications audio. Si vous avez déjà implémenté la qualité de service (QoS) et que vous utilisez un autre code DSCP pour l’audio (par exemple, DSCP 40), vous devez configurer votre politique de qualité de service pour utiliser ce code (c’est-à-dire 40 pour le son). Si vous implémentez actuellement la qualité de service, nous vous conseillons d’utiliser le DSCP 46 pour l’audio, car cette valeur est couramment utilisée pour marquer les paquets audio.

Une fois que vous avez créé la stratégie de QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo (et, éventuellement, une troisième stratégie de gestion du trafic de partage d’application). Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype entreprise Server Video**).

  - Définissez la valeur DSCP sur **34** au lieu de 46. (Notez que vous n’avez pas besoin d’utiliser une valeur DSCP de 34. La seule condition requise est d’utiliser une autre valeur DSCP pour la vidéo que celle utilisée pour l’audio.

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé ports 57501 à 65535 pour la vidéo, définissez l’intervalle de ports comme suit: **57501:65535**.

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **partage d’application Skype entreprise Server**).

  - Définissez la valeur DSCP sur **24** au lieu de 46. (De nouveau, vous n’avez pas besoin d’utiliser une valeur DSCP de 24. La seule condition requise est d’utiliser une autre valeur DSCP pour le partage d’application que celle utilisée pour l’audio ou la vidéo.)

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé ports 40803 à 49151 pour le partage d’application, définissez l’intervalle de ports comme suit: **40803:49151**.

Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur vos ordinateurs Skype entreprise Server. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée:

    Gpupdate.exe /force

Vous pouvez exécuter cette commande à partir de Skype entreprise Server Management Shell ou depuis n’importe quelle fenêtre de commande exécutée sous informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

Pour vérifier que les nouvelles stratégies de QoS sont appliquées, procédez comme suit:

1.  Sur un ordinateur Skype entreprise Server, cliquez sur **Démarrer**, puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez **ordinateur**, sur **\_HKEY local\_machine**, développez **logiciel**, développez **stratégies**, développez **Microsoft**, développez **Windows**, puis cliquez sur **QoS**. Sous **QoS** , vous devez voir les clés de Registre correspondant aux stratégies de QoS que vous venez de créer. Par exemple, si vous avez créé deux nouvelles stratégies (l’une ayant pour nom audio Skype entreprise Server QoS et l’autre appelée Skype entreprise Server Video QoS), vous devez voir les entrées de Registre pour Skype entreprise Server audio QoS et la qualité de service vidéo de Skype entreprise Server.

Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante:

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Une fois la nouvelle valeur du Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre et redémarrez votre ordinateur.
