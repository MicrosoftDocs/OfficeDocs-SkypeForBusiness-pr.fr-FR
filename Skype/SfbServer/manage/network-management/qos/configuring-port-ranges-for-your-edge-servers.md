---
title: Configuration des plages de ports et une qualité de Service pour vos serveurs Edge
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article décrit comment configurer les plages de ports pour les serveurs Edge et comment configurer une stratégie de qualité de Service pour votre A / V les serveurs de périphérie.
ms.openlocfilehash: 11fdb542c6256c21e169480194bc5154bf1c1428
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214932"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configuration des plages de ports et d’une stratégie de qualité de Service pour vos serveurs Edge dans Skype pour Business Server

Cet article décrit comment configurer les plages de ports pour les serveurs Edge et comment configurer une stratégie de qualité de Service pour votre A / V les serveurs de périphérie.

## <a name="configure-port-ranges"></a>Configurer les plages de ports

Avec les serveurs de périphérie, vous n’avez pas configurer les plages de ports distincts pour les paramètres audio, vidéo et partage d’application ; de même, les plages de ports utilisées pour les serveurs Edge n’ont pas à respecter les plages de ports utilisées avec vos serveurs de conférence, d’Application et de médiation. Avant de poursuivre avec notre exemple, il est important de souligner que cette option existe, mais nous vous recommandons vous ne modifiez pas les plages de ports, comme cela peut influer sur certains scénarios si vous déplacez en dehors de la plage de 50000 ports.

Par exemple, supposons que vous avez configuré vos serveurs de conférence, d’Application et de médiation pour utiliser ces plages de ports :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de paquet</th>
<th>Port de début</th>
<th>Nombre de Ports réservés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totaux</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Comme vous pouvez le constater, votre port plages pour l’audio, vidéo, partage d’application et commencer à port 40803 et englober un total de 24732 ports. Si vous préférez, vous pouvez configurer un serveur Edge donné pour utiliser les valeurs de port global en exécutant une commande semblable à celui-ci dans le Skype pour Business Server Management Shell :

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Ou, utilisez la commande suivante pour configurer simultanément tous les serveurs Edge dans votre organisation :

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Vous pouvez vérifier les paramètres de port actuels de vos serveurs Edge à l’aide de cette Skype de commande Business Server Management Shell :

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Encore une fois, tandis que nous ne fournissent pas ces options, il est vivement recommandé que vous laissez les éléments qu’ils sont pour la configuration de port.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurer une stratégie de QoS pour votre A / V les serveurs de périphérie

Outre la création de stratégies QoS pour vos serveurs de conférence, d’Application et de médiation, vous devez également créer des stratégies audio et vidéos du côté interne de votre A / V servers périphériques. Toutefois, les stratégies utilisées sur vos serveurs Edge sont différentes des stratégies utilisés sur vos serveurs de conférence, d’Application et de médiation. Pour les serveurs de conférence, d’Application et de médiation, vous avez spécifié une plage de ports source ; avec les serveurs de périphérie, vous devez spécifier une plage de ports de destination. Pour cette raison, vous ne peuvent pas simplement appliquer les stratégies de QoS serveur de conférence, d’Application et de médiation pour vos serveurs Edge : ces stratégies ne fonctionnent. Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer les stratégies pour vos serveurs Edge uniquement.

La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisées pour gérer la qualité de Service sur les serveurs Edge. Bien sûr, il est possible que vos serveurs Edge sont des serveurs autonomes qui n’ont pas de comptes Active Directory. Si tel est le cas, vous pouvez utiliser la stratégie de groupe locale au lieu de la stratégie de groupe Active Directory : la seule différence est que vous devez créer ces stratégies locales à l’aide de l’éditeur de stratégie de groupe locale et devez créer individuellement le même ensemble de stratégies sur chaque serveur Edge. Pour démarrer l’éditeur de stratégie de groupe Local sur un serveur Edge, procédez comme suit :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **gpedit.msc**, puis appuyez sur ENTRÉE.

Si vous créez des stratégies basées sur Active Directory, puis vous devez session sur un ordinateur où la gestion des stratégies de groupe a été installée. Dans ce cas, ouvrez Gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestion des stratégies de groupe**), puis suivez les étapes suivantes :

1.  Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée. Par exemple, si tous vos Skype pour les ordinateurs Business Server se trouvent dans une unité d’organisation nommée Skype pour Business Server, la nouvelle stratégie doit être créée en la Skype pour l’unité d’organisation du serveur Business.

2.  Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.

3.  Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Skype pour Business Server Audio**), puis cliquez sur **OK**.

4.  Avec le bouton droit de la stratégie créée, puis cliquez sur **Modifier**.

À partir de là, le processus est identique quelle que soit la création d’une stratégie Active Directory ou une stratégie locale :

1.  Dans l’éditeur de gestion de stratégie de groupe ou l’éditeur de stratégie de groupe, développez **Configuration ordinateur**, développez **stratégies**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

2.  Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie (par exemple, **Skype pour Business Server Audio**) dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**. Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.

3.  Dans la page suivante, vérifiez que **toutes les applications** est sélectionné, puis cliquez sur **suivant**. Ce paramètre indique le réseau pour rechercher tous les paquets avec un marquage DSCP des paquets pas seulement 46, créé par une application spécifique.

4.  Dans la troisième page, assurez-vous que **toute adresse IP source** et **n’importe quelle adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**. Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.

5.  Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau plus couramment utilisés par Skype pour Business Server et ses applications clientes.

6.  Sous le titre, **Spécifiez le numéro de port de destination**, sélectionnez **à partir de ce port de destination ou la plage**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservé ports 49152 par le biais de ports 57500 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **49152:57500**. Cliquez sur **Terminer**.

Une fois que vous avez créé la stratégie QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo. Pour créer une stratégie pour la vidéo, suivez la même procédure de base que vous avez suivi lors de la création de la stratégie audio, effectuant les substitutions :

  - Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour Business Server vidéo**).

  - Définissez la valeur DSCP **34** au lieu de 46. (Notez que vous n’avez pas d’utiliser une valeur DSCP de 34. La seule exigence est que vous utilisez une autre valeur DSCP pour la vidéo que vous avez utilisé pour l’audio.)

  - Utiliser la plage de ports précédemment configuré pour le trafic vidéo. Par exemple, si vous avez réservé ports 57501 et 65 535 pour la vidéo, définissez la plage de ports à ceci : **57501:65535**. Là encore, il doit être configurée en tant que la plage de ports de destination.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :

  - Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour le partage d’Application Business Server**).

  - Définissez la valeur DSCP à **24** au lieu de 46. (Là encore, il est inutile d’utiliser une valeur DSCP sur 24. La seule exigence est que vous utilisez une autre valeur DSCP pour le partage d’application que vous avez utilisé pour l’audio ou vidéo.)

  - Utiliser la plage de ports précédemment configuré pour le trafic vidéo. Par exemple, si vous avez réservé ports 40803 via et 49 151 partage d’application, définissez la plage de ports à ceci : **40803:49151**.

Les nouvelles stratégies que vous avez créé ne prendra pas effet tant que la stratégie de groupe a été actualisée sur vos serveurs de périphérie. Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur où la stratégie de groupe doivent être actualisées :

    Gpudate.exe /force

Cette commande peut être exécutée à partir de dans la Skype pour Business Server ou à partir de n’importe quelle fenêtre de commande s’exécutant sous les informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez sur **invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Notez que vous devrez peut-être redémarrer le serveur de périphérie même après l’exécution de Gpudate.exe.

Pour garantir que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en procédant comme suit :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_ordinateur**, développez **système**, développez **CurrentControlSet**, développez **services**et **puis TCPIP**.

4.  Cliquez sur **TCP/IP**, pointez sur **Nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre est créée, tapez **QoS**, puis appuyez sur ENTRÉE pour renommer la clé.

5.  Avec le bouton droit **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**. Une fois la nouvelle valeur de Registre est créée, tapez **n’utilisez pas l’authentification réseau**, puis appuyez sur ENTRÉE pour renommer la valeur.

6.  Double-cliquez sur **n’utilisent pas authentification réseau**. Dans la boîte de dialogue **Modification de la chaîne** , tapez **1** dans la zone **valeur** , puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et redémarrez votre ordinateur.
