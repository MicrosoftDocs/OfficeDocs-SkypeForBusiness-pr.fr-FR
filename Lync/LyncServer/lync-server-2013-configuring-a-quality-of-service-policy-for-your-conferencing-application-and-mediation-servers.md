---
title: 'Lync Server 2013 : Configuration d’une stratégie de qualité de service pour les serveurs de conférence, d’application et de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a79835fb19f5a30a11eac4859f133aeec5c8cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configuration d’une stratégie de qualité de service dans Lync Server 2013 pour les serveurs de conférence, d’application et de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-23_

La configuration de plages de ports facilite l’utilisation de la qualité de service en s’assurant que tout le trafic d’un type spécifique (par exemple, tout le trafic audio) est acheminé par le même ensemble de ports. Ainsi, le système peut facilement identifier et marquer un paquet donné: si le port 49152 est réservé au trafic audio, tout paquet transmis via le port 49152 peut être marqué avec un code DSCP indiquant qu’il s’agit d’un paquet audio. Cela permet aux routeurs d’identifier le paquet en tant que paquet audio et de lui attribuer une priorité plus élevée que les paquets non marqués (par exemple, les paquets utilisés pour copier un fichier d’un serveur vers un autre).

En revanche, le simple fait de limiter un ensemble de ports à un type spécifique de trafic n’entraîne pas le passage de paquets avec le code DSCP approprié. En plus de définir des plages de ports, vous devez également créer des politiques de qualité de service qui spécifient le code DSCP à associer à chaque plage de ports. Pour Microsoft Lync Server 2013, il s’agit généralement de créer deux stratégies: une pour le son et une pour la vidéo.

Les stratégies de qualité de service sont plus faciles à créer et à gérer via une stratégie de groupe. (Ces mêmes stratégies peuvent également être créées à l’aide de stratégies de sécurité locales. Toutefois, vous devez répéter la même procédure sur chacun d’eux et sur tous les ordinateurs.) Votre ensemble initial de stratégies de QoS (une pour le son et l’autre pour la vidéo) ne doit être appliqué qu’aux ordinateurs Lync Server exécutant le serveur de conférence, le serveur d’applications et/ou les services de médiation Server. Si tous ces ordinateurs sont situés dans le même UO d’annuaire Active Directory, vous pouvez simplement affecter le nouvel objet de stratégie de groupe à cette unité d’organisation. Vous pouvez également effectuer d’autres opérations pour cibler la nouvelle stratégie sur les ordinateurs spécifiques. par exemple, vous pouvez placer les ordinateurs appropriés dans un groupe de sécurité, puis utiliser le filtrage de la sécurité de la stratégie de groupe pour appliquer l’objet de stratégie de groupe à ce groupe de sécurité.

Pour créer une stratégie de qualité de service pour la gestion du son, connectez-vous à un ordinateur sur lequel est installée la gestion des stratégies de groupe. Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit:

1.  Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs serveur Lync résident dans une unité d’organisation nommée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et associez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , tapez le nom du nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Lync Server QoS**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

5.  Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **stratégies**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée** sur une stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **Lync Server QoS**) dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

7.  Dans la page suivante, assurez-vous que l’option **toutes les applications** est sélectionnée, puis cliquez sur **suivant**. Cela permet de s’assurer que toutes les applications correspondent aux paquets de la plage de ports spécifiée avec le code DSCP spécifié.

8.  Sur la troisième page, assurez-vous que toutes les **adresses IP source et adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.

9.  Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Lync Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 49152 via ports 57500 pour le trafic audio, entrez la plage de ports à l’aide du format suivant: **49152:57500**. Cliquez sur **Terminer**.

<div>


> [!NOTE]  
> La valeur DSCP de 46 est légèrement arbitraire: bien que le DSCP 46 soit souvent utilisé pour marquer les paquets audio, vous ne devez pas utiliser DSCP 46 pour les communications audio. Si vous avez déjà implémenté la qualité de service (QoS) et que vous utilisez un autre code DSCP pour l’audio (par exemple, DSCP 40), vous devez configurer votre stratégie de qualité de service pour utiliser ce code (c’est-à-dire 40 pour le son). Si vous implémentez actuellement la qualité de service, nous vous conseillons d’utiliser le DSCP 46 pour l’audio, car cette valeur est couramment utilisée pour marquer les paquets audio.



</div>

Une fois que vous avez créé la stratégie de QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo (et éventuellement une troisième stratégie de gestion du trafic de partage d’application). Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Lync Server Video**).

  - Définissez la valeur DSCP sur **34** au lieu de 46. (Notez que vous n’avez pas besoin d’utiliser une valeur DSCP de 34. La seule condition requise est d’utiliser une autre valeur DSCP pour la vidéo que celle utilisée pour l’audio.

  - Utilisez la plage de ports déjà configurée pour le trafic vidéo. Par exemple, si vous avez réservé ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme suit: **57501:65535**.

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, le **partage d’applications serveur Lync**).

  - Définissez la valeur DSCP sur **24** au lieu de 46. (De nouveau, vous n’avez pas besoin d’utiliser une valeur DSCP de 24. La seule condition requise est d’utiliser une autre valeur DSCP pour le partage d’application que celle utilisée pour l’audio ou la vidéo.)

  - Utilisez la plage de ports déjà configurée pour le trafic vidéo. Par exemple, si vous avez réservé ports 40803 à 49151 pour le partage d’application, définissez l’intervalle de ports comme suit: **40803:49151**.

Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur vos ordinateurs serveur Lync. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée:

    Gpupdate.exe /force

Vous pouvez exécuter cette commande à partir de Lync Server Management Shell ou à partir de n’importe quelle fenêtre de commande qui s’exécute sous informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

Pour vérifier que les nouvelles stratégies de QoS sont appliquées, procédez comme suit:

1.  Sur un ordinateur serveur Lync, cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez **ordinateur**, sur **\_HKEY local\_machine**, développez **logiciel**, développez **stratégies**, développez **Microsoft**, développez **Windows**, puis cliquez sur **QoS**. Sous **QoS** , vous devez voir les clés de Registre correspondant aux stratégies de QoS que vous venez de créer. Par exemple, si vous avez créé deux nouvelles stratégies (l’une ayant pour nom QoS du serveur audio Lync Server et l’autre nommée QoS vidéo de Lync Server Video QoS), vous devez les entrées de Registre pour la qualité de service audio de Lync Server et la qualité QoS vidéo de Lync Server.

Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante:

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Après la création de la nouvelle valeur du Registre, tapez **ne pas utiliser NLA** , puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre, puis redémarrez votre ordinateur.

</div>

<span> </span>

</div>

</div>

</div>

