---
title: 'Lync Server 2013 : configuration des stratégies de qualité de service pour les clients exécutant Windows 7 ou Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc06f5079fc6876c85324af67bd22be12f85a3c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients exécutant Windows 7 ou Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-29_

Outre la spécification des plages de port destinées aux clients Lync, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients. (La qualité de service créée pour les serveurs de conférence, d’application et de médiation ne doit pas être appliquée aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Lync 2013 et Windows 7 ou Windows 8.

L’exemple suivant utilise ce jeu de plages de ports pour créer une stratégie audio et une stratégie de vidéo :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Début du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>CX3-20</p></td>
</tr>
</tbody>
</table>


Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 7 ou Windows 8, vous devez d’abord vous connecter à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit :

1.  Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et associez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , tapez le nom du nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **audio Lync**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

5.  Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **stratégies**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **audio Lync**) dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

7. Sur la page suivante, sélectionnez **uniquement les applications avec ce nom d’exécutable** et entrez le nom **Lync. exe**, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant du client Lync.

8.  Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.

9.  Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Lync Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 50020 via ports 50039 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **50020:50039**. Cliquez sur **Terminer**.

Une fois que vous avez créé la stratégie QoS pour le son, vous devez créer une deuxième stratégie pour la vidéo. Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **vidéo Lync**).

  - Définissez la valeur DSCP sur **34** au lieu de 46. (Comme indiqué précédemment, vous n’avez pas besoin d’utiliser la valeur DSCP 34 ; il vous suffit d’affecter une valeur DSCP différente de celle utilisée pour l’audio.)

  - Utilisez la plage de ports déjà configurée pour le trafic vidéo. Par exemple, si vous avez réservé ports 58000 à 58019 pour la vidéo, définissez la plage de ports comme suit : **58000:58019**.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, procédez comme suit :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, le **partage d’applications serveur Lync**).

  - Définissez la valeur DSCP sur **24** au lieu de 46. (De nouveau, cette valeur ne doit pas être de 24 ; il doit simplement être différent des valeurs DSCP utilisées pour l’audio et la vidéo.)

  - Utilisez la plage de ports déjà configurée pour le trafic vidéo. Par exemple, si vous avez réservé ports 42000 à 42019 pour le partage d’application, définissez l’intervalle de ports comme suit : **42000:42019**.

Pour une stratégie de transfert de fichiers :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Lync Server**).

  - Définissez la valeur DSCP sur **14**. (De nouveau, cette valeur ne doit pas être 14 ; il doit simplement s’agir d’un code DSCP unique.)

  - Utilisez la plage de ports déjà configurée pour l’application. Par exemple, si vous avez réservé ports 42020 à 42039 pour le partage d’application, définissez l’intervalle de ports comme suit : **42020:42039**.

Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur les ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée :

    Gpudate.exe /force

Vous pouvez exécuter cette commande à partir de n’importe quelle fenêtre de commande exécutée sous informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

Gardez à l’esprit que ces stratégies doivent être ciblées vers les ordinateurs clients. Ils ne doivent pas être appliqués aux serveurs exécutant Lync Server.

Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante :

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Après la création de la nouvelle valeur du Registre, tapez **ne pas utiliser NLA** , puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre, puis redémarrez votre ordinateur.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configuration de la qualité de service sur des ordinateurs dotés de plusieurs cartes réseau

Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, vous risquez de rencontrer des problèmes pour lesquels les valeurs DSCP apparaissent sous la forme de 0x00 au lieu de la valeur configurée. Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs des cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé). Dans les cas similaires, les valeurs DSCP seront balisées pour les adaptateurs qui peuvent accéder au domaine, mais ne seront pas balisés pour les cartes qui ne peuvent pas accéder au domaine.

Si vous souhaitez baliser les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Après la création de la nouvelle valeur du Registre, tapez **ne pas utiliser NLA** , puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur pour que les modifications soient prises en compte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

