---
title: Configuration de plages de ports et d’une qualité de service pour vos serveurs de périphérie
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: Cet article décrit la configuration des plages de port pour les serveurs Edge et la configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V.
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817433"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de périmètre dans Skype entreprise Server

Cet article décrit la configuration des plages de port pour les serveurs Edge et la configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V.

## <a name="configure-port-ranges"></a>Configurer des plages de ports

Sur les serveurs de périphérie, vous n’avez pas besoin de configurer des plages de port distinctes pour le partage audio, vidéo et d’application. de même, les plages de port utilisées pour les serveurs Edge ne doivent pas nécessairement correspondre aux plages de port utilisées avec vos serveurs de conférence, d’application et de médiation. Avant de continuer, nous vous conseillons de faire ressortir le fait que, si vous dépassez cette option, nous vous conseillons de ne pas modifier les plages de ports, car cela risque de dégrader certains scénarios si vous vous éloignez de la plage de ports 50000.

Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’application et de médiation pour utiliser ces plages de ports :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de paquet</th>
<th>Port de démarrage</th>
<th>Nombre de ports réservés</th>
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


Comme vous pouvez le constater, vos plages de port pour le partage audio, vidéo et d’application commencent au port 40803 et incluent au total des ports 24732. Si vous le souhaitez, vous pouvez configurer un serveur Edge pour utiliser ces valeurs de port globales en exécutant une commande similaire à celle-ci dans la base de données Skype entreprise Server Management Shell :

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Vous pouvez utiliser la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation :

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Vous pouvez vérifier les paramètres de port actuels pour vos serveurs Edge en utilisant la commande Skype entreprise Server Management Shell suivante :

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Là encore, nous vous conseillons vivement de conserver les éléments tels que la configuration de port.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurer une stratégie de QoS pour vos serveurs Edge A/V

Outre la création de stratégies de QoS pour vos serveurs de conférence, d’application et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs de frontière A/V. Toutefois, les stratégies utilisées sur les serveurs de périphérie sont différentes de celles utilisées sur les serveurs de conférences, d’applications et de médiation. Pour les serveurs de conférence, d’application et de médiation, vous avez spécifié une plage de ports sources ; Si vous avez un serveur Edge, vous devez spécifier la plage de ports de destination. C’est la raison pour laquelle vous ne pouvez pas appliquer les stratégies QoS du serveur de conférence, d’application et de médiation aux serveurs de périphérie : ces stratégies ne fonctionneront simplement pas. Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer ces stratégies uniquement aux serveurs Edge.

La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisés pour gérer la qualité du service sur les serveurs Edge. Bien entendu, il est possible que vos serveurs Edge sont des serveurs autonomes qui ne disposent pas de comptes Active Directory. Si tel est le cas, vous pouvez utiliser une stratégie de groupe locale au lieu de la stratégie de groupe Active Directory : la seule différence réside dans le fait que vous devez créer ces stratégies locales à l’aide de l’éditeur de stratégies de groupe local, et créer individuellement le même ensemble de stratégies sur chaque serveur Edge. Pour démarrer l’éditeur d’une stratégie de groupe locale sur un serveur Edge, procédez comme suit :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **gpedit. msc**, puis appuyez sur entrée.

Si vous créez des stratégies basées sur Active Directory, vous devez vous connecter à un ordinateur sur lequel est installée la gestion des stratégies de groupe. Dans ce cas, ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur gestion de la **stratégie de groupe**), puis procédez comme suit :

1.  Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs Skype entreprise Server résident dans une unité d’organisation nommée Skype entreprise Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Skype entreprise Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , tapez le nom du nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Skype entreprise Server audio**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

À partir de là, le processus est identique, que vous soyez ou non à la création d’une stratégie Active Directory ou d’une stratégie locale :

1.  Dans l’éditeur de gestion des stratégies de groupe ou dans l’éditeur de stratégies de groupe local, développez Configuration de l' **ordinateur**, développez **stratégies**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

2.  Dans la boîte de dialogue **QoS basée** sur une stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **Skype entreprise Server audio**) dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

3.  Dans la page suivante, assurez-vous que l’option **toutes les applications** est sélectionnée, puis cliquez sur **suivant**. Ce paramètre indique au réseau de chercher tous les paquets avec un marquage DSCP de 46, pas seulement les paquets créés par une application spécifique.

4.  Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.

5.  Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Skype entreprise Server et ses applications clientes.

6.  Sous le titre **Spécifiez le numéro de port de destination**, faites votre choix **dans la plage ou le port de destination**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 49152 via ports 57500 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **49152:57500**. Cliquez sur **Terminer**.

Une fois que vous avez créé la stratégie QoS pour le trafic audio, vous devez créer une seconde stratégie pour le trafic vidéo. Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype entreprise Server Video**).

  - Définissez la valeur DSCP sur **34** au lieu de 46. (Notez que vous n’avez pas besoin d’utiliser une valeur DSCP de 34. La seule condition requise est d’utiliser une autre valeur DSCP pour la vidéo que celle utilisée pour l’audio.

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé ports 57501 à 65535 pour la vidéo, définissez l’intervalle de ports comme suit : **57501:65535**. Là encore, cela doit être configuré comme plage de ports de destination.

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **partage d’application Skype entreprise Server**).

  - Définissez la valeur DSCP sur **24** au lieu de 46. (De nouveau, vous n’avez pas besoin d’utiliser une valeur DSCP de 24. La seule condition requise est d’utiliser une autre valeur DSCP pour le partage d’application que celle utilisée pour l’audio ou la vidéo.)

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé ports 40803 à 49151 pour le partage d’application, définissez l’intervalle de ports comme suit : **40803:49151**.

Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur votre serveur Edge. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée :

    Gpudate.exe /force

Vous pouvez exécuter cette commande à partir du serveur Skype entreprise ou depuis n’importe quelle fenêtre de commande exécutée sous informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**. Notez qu’il se peut que vous deviez redémarrer le serveur Edge même après avoir exécuté gpudate. exe.

Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Une fois la nouvelle valeur du Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre et redémarrez votre ordinateur.
