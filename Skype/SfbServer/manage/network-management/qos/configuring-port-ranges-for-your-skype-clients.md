---
title: Configuration de plages de ports et d’une stratégie de qualité de service pour vos clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article décrit la configuration des plages de port pour vos clients et la configuration des stratégies de qualité de service dans Skype entreprise Server pour les clients exécutant Windows 10.
ms.openlocfilehash: 4d7999634864e222dd627ea3b46a3a3da5c67fe5
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2019
ms.locfileid: "35841468"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuration de plages de ports et d’une politique de qualité de service pour vos clients dans Skype entreprise Server

Cet article décrit la configuration des plages de port pour vos clients et la configuration des stratégies de qualité de service dans Skype entreprise Server pour les clients exécutant Windows 10.

## <a name="configure-port-ranges"></a>Configurer des plages de ports

Par défaut, les applications clientes Skype entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsque vous participez à une session de communication. en effet, les plages de port spécifiques ne sont pas activées automatiquement pour les clients. Toutefois, pour pouvoir utiliser la qualité de service, vous devez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et transfert de fichier) à une série de plages de ports uniques. Pour ce faire, vous pouvez utiliser l’applet de passe Set-CsConferencingConfiguration.

> [!NOTE]  
> Les utilisateurs finaux ne peuvent pas apporter ces modifications. Les modifications de port ne peuvent être effectuées que par les administrateurs utilisant l’applet de cmdlet Set-CsConferencingConfiguration.


Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Skype entreprise Server Management Shell:

    Get-CsConferencingConfiguration

En supposant que vous n’avez apporté aucune modification à vos paramètres de conférence depuis que vous avez installé Skype entreprise Server, vous devez obtenir des informations sur les propriétés suivantes:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si vous observez de près la sortie précédente, vous verrez deux points importants. Tout d’abord, la propriété ClientMediaPortRangeEnabled est définie sur false:

    ClientMediaPortRangeEnabled : False

C’est un point important, car lorsque cette propriété est définie sur false, les clients Skype entreprise utiliseront tout port disponible entre les ports 1024 et 65535 lors d’une session de communication; C’est vrai, quels que soient les autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort). Si vous souhaitez restreindre l’utilisation à un ensemble spécifique de ports (ce que vous voulez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de port de média client. Vous pouvez effectuer cette opération à l’aide de la commande Windows PowerShell suivante:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

La commande précédente permet d’activer les plages de port de média client pour la collection globale de paramètres de configuration de conférence. Toutefois, ces paramètres peuvent également être appliqués à l’étendue du site et/ou à l’étendue du service (pour le service du serveur de conférence uniquement). Pour activer les plages de port de média client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Vous pouvez également utiliser cette commande pour activer simultanément les plages de ports pour tous les paramètres de configuration de la Conférence:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Le deuxième élément important que vous remarquerez est que la sortie de l’exemple indique que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Pour implémenter QoS, chacune de ces plages de port doit être unique. Par exemple, vous pouvez configurer les plages de ports comme suit:


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


Dans le tableau ci-dessus, les plages de port client représentent un sous-ensemble des plages de ports configurées pour vos serveurs. Par exemple, sur les serveurs, le partage d’application a été configuré de manière à utiliser les ports 40803 à 49151; sur les ordinateurs clients, le partage d’application est configuré de manière à utiliser les ports 42000 à 42019. C’est aussi essentiellement pour faciliter l’administration de la qualité de service (QoS): les ports clients n’ont pas besoin de représenter un sous-ensemble de ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application à utiliser, par exemple, les ports 10000 à 10019.) Néanmoins, nous vous conseillons de faire en sorte que les plages de port de votre client constituent un sous-ensemble de vos plages de port serveur.

Par ailleurs, vous avez peut-être remarqué que les ports 8348 étaient mis de côté pour le partage d’application sur les serveurs, mais que seuls 20 ports étaient mis de côté pour le partage d’application sur les clients. C’est également recommandé, mais n’est pas une règle matérielle et rapide. En règle générale, vous pouvez considérer chaque port disponible pour représenter une seule session de communication: Si vous disposez de ports 100 disponibles dans une plage de port, cela signifie que l’ordinateur en question peut, au plus, des sessions de communication 100 à tout moment. Étant donné que les serveurs seront susceptibles de participer dans de nombreuses conversations qu’aux clients, il est préférable d’ouvrir de nombreux ports supplémentaires sur les serveurs plutôt que sur les clients. La mise en place de 20 ports pour le partage d’application sur un client implique qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, en même temps. Cela devrait s’avérer suffisant pour la plupart de vos utilisateurs.

Pour affecter les plages de port précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande suivante de Skype entreprise Server Management Shell:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Vous pouvez utiliser cette commande pour affecter les mêmes plages de ports à tous les paramètres de configuration de la Conférence:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Les utilisateurs individuels doivent se déconnecter de Skype entreprise, puis se reconnecter pour que les modifications soient prises en compte.

> [!NOTE]  
> Vous pouvez également activer les plages de port de média client, puis les affecter à l’aide d’une seule commande. Par exemple :<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurer des stratégies de qualité de service pour les clients qui s’exécutent sur Windows 10

En plus de spécifier des plages de port destinées aux clients Skype entreprise, vous devez également créer des politiques de qualité de service distinctes qui seront appliquées aux ordinateurs clients. (La qualité de service créée pour les serveurs de conférence, d’application et de médiation ne doit pas être appliquée aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Skype entreprise et Windows 10.

L’exemple suivant utilise ce jeu de plages de ports pour créer une stratégie audio et une stratégie de vidéo:


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

Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 10, vous devez d’abord vous connecter à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit:

1.  Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

5.  Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

7.  Dans la page suivante, sélectionnez **uniquement les applications ayant ce nom d’exécutable**, entrez **Lync. exe** comme nom, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant à partir du client Skype entreprise.

8.  Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.

9.  Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Skype entreprise Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 50020 via ports 50039 pour le trafic audio, entrez la plage de ports à l’aide du format suivant: **50020:50039**. Cliquez sur **Terminer**.

Une fois que vous avez créé la stratégie QoS pour le son, vous devez créer une deuxième stratégie pour la vidéo. Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique).

  - Définissez la valeur DSCP sur **34** au lieu de 46. (Comme indiqué précédemment, vous n’avez pas besoin d’utiliser la valeur DSCP 34; il vous suffit d’affecter une valeur DSCP différente de celle utilisée pour l’audio.)

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé ports 58000 à 58019 pour la vidéo, définissez l’intervalle de ports comme suit: **58000:58019**.

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, effectuez les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **partage d’application Skype entreprise Server**).

  - Définissez la valeur DSCP sur **24** au lieu de 46. (De nouveau, cette valeur ne doit pas être de 24; il doit simplement être différent des valeurs DSCP utilisées pour l’audio et la vidéo.)

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé ports 42000 à 42019 pour le partage d’application, définissez l’intervalle de ports comme suit: **42000:42019**.

Pour une stratégie de transfert de fichiers:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Skype entreprise Server**).

  - Définissez la valeur DSCP sur **14**. (De nouveau, cette valeur ne doit pas être 14; il doit simplement s’agir d’un code DSCP unique.)

  - Utilisez la plage de port précédemment configurée pour l’application. Par exemple, si vous avez réservé ports 42020 à 42039 pour le partage d’application, définissez l’intervalle de ports comme suit: **42020:42039**.

Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur les ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée:

    Gpupdate.exe /force

Vous pouvez exécuter cette commande à partir de n’importe quelle fenêtre de commande exécutée sous informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

Gardez à l’esprit que ces stratégies doivent être ciblées vers les ordinateurs clients. Ils ne doivent pas être appliqués aux serveurs exécutant Skype entreprise Server.

Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante:

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Une fois la nouvelle valeur du Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre et EBOOT votre ordinateur.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurer la qualité de service sur des ordinateurs dotés de plusieurs cartes réseau

Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, il est possible que vous rencontriez des problèmes de valeurs DSCP au lieu de la valeur configurée. Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs des cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé). Dans les cas similaires, les valeurs DSCP seront balisées pour les adaptateurs qui peuvent accéder au domaine, mais ne seront pas balisés pour les cartes qui ne peuvent pas accéder au domaine.

Si vous souhaitez baliser les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre. Pour cela, procédez comme suit:

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Une fois la nouvelle valeur du Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur pour que les modifications prennent effet.

## <a name="see-also"></a>Voir aussi

[Créer un objet de stratégie de groupe dans Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
