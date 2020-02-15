---
title: Configuration des plages de ports et d’une stratégie de qualité de service pour vos clients
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article explique comment configurer des plages de ports pour vos clients et configurer des stratégies de qualité de service dans Skype entreprise Server pour les clients s’exécutant sur Windows 10.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045887"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuration des plages de ports et d’une stratégie de qualité de service pour vos clients dans Skype entreprise Server

Cet article explique comment configurer des plages de ports pour vos clients et configurer des stratégies de qualité de service dans Skype entreprise Server pour les clients s’exécutant sur Windows 10.

## <a name="configure-port-ranges"></a>Configurer les plages de ports

Par défaut, les applications clientes Skype entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsqu’une session de communication est impliquée. Cela est dû au fait que les plages de ports spécifiques ne sont pas automatiquement activées pour les clients. Pour utiliser la qualité de service, toutefois, vous devrez réaffecter les différents types de trafic (audio, vidéo, multimédia, partage d’application et transfert de fichiers) à une série de plages de ports uniques. Cette opération peut être réalisée à l’aide de la cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Les utilisateurs finaux ne peuvent pas procéder à ces modifications. Les modifications apportées aux ports peuvent être effectuées uniquement par les administrateurs à l’aide de la cmdlet Set-CsConferencingConfiguration.


Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Skype entreprise Server Management Shell :

    Get-CsConferencingConfiguration

En supposant que vous n’avez apporté aucune modification à vos paramètres de conférence depuis que vous avez installé Skype entreprise Server, vous devez obtenir des informations telles que les valeurs de ces propriétés :

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si vous examinez attentivement la sortie précédente, vous verrez deux éléments d’importance. Tout d’abord, la propriété paramètres clientmediaportrangeenabled est définie sur false :

    ClientMediaPortRangeEnabled : False

Cela est important car, lorsque cette propriété est définie sur false, les clients Skype entreprise utiliseront n’importe quel port disponible entre les ports 1024 et 65535 lorsqu’ils participent à une session de communication. Cela est vrai indépendamment des autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort). Si vous souhaitez restreindre l’utilisation à un ensemble spécifique de ports (ce que vous devez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de ports du client multimédia. Cela peut être réalisé à l’aide de la commande Windows PowerShell suivante :

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

La commande précédente permet d’activer des plages de ports multimédias client pour la collection globale des paramètres de configuration de conférence ; Toutefois, ces paramètres peuvent également être appliqués à l’étendue du site et/ou à l’étendue du service (pour le service de serveur de conférence uniquement). Pour activer des plages de ports multimédias client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration :

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Vous pouvez également utiliser cette commande pour activer simultanément les plages de ports pour tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La deuxième chose d’importance que vous remarquerez est que le résultat de l’exemple indique que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques :

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Pour mettre en œuvre la qualité de service, chacune de ces plages de ports doit être unique. Par exemple, vous pouvez configurer les plages de ports comme suit :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Démarrage du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>vingtaine</p></td>
</tr>
</tbody>
</table>


Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurées pour vos serveurs. Par exemple, sur les serveurs, le partage d’application a été configuré pour utiliser les ports 40803 à 49151 ; sur les ordinateurs clients, le partage d’application est configuré pour utiliser les ports 42000 à 42019. Cette opération est également réalisée principalement pour faciliter l’administration de la qualité de service (QoS) : les ports clients n’ont pas besoin de représenter un sous-ensemble des ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application à utiliser, par exemple, les ports 10000 à 10019.) Toutefois, il est recommandé de faire en sorte que les plages de ports clients soient un sous-ensemble des plages de ports de votre serveur.

De plus, vous avez peut-être remarqué que les ports 8348 ont été mis de côté pour le partage d’application sur les serveurs, mais seulement 20 ports ont été mis de côté pour le partage d’application sur les clients. Il est également recommandé de le faire, mais il ne s’agit pas d’une règle rapide. En règle générale, vous pouvez considérer chaque port disponible pour qu’il représente une seule session de communication : Si vous disposez de 100 ports disponibles dans une plage de ports, cela signifie que l’ordinateur en question peut, au plus, prendre part à 100 sessions de communication à tout moment. Étant donné que les serveurs feront probablement partie d’autres conversations que les clients, il est logique d’ouvrir beaucoup plus de ports sur les serveurs que sur les clients. Le fait de ne pas mettre en place 20 ports pour le partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, tout en même temps. Cela doit s’avérer suffisant pour la grande majorité de vos utilisateurs.

Pour affecter les plages de ports précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande suivante de Skype entreprise Server Management Shell :

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Vous pouvez utiliser cette commande pour affecter ces mêmes plages de ports à tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Les utilisateurs individuels doivent se déconnecter de Skype entreprise, puis se reconnecter pour que ces modifications prennent effet.

> [!NOTE]  
> Vous pouvez également activer les plages de ports multimédias client, puis affecter ces plages de ports à l’aide d’une seule commande. Par exemple :<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurer les stratégies de qualité de service pour les clients s’exécutant sur Windows 10

En plus de spécifier des plages de ports pour les clients Skype entreprise, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients. (Les stratégies de qualité de service créées pour les serveurs de conférence, d’application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Skype entreprise et Windows 10.

L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Démarrage du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>vingtaine</p></td>
</tr>
</tbody>
</table>

Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 10, connectez-vous d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **gestion des stratégies de groupe**), puis procédez comme suit :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine, puis liez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **modifier**.

5.  Dans l’éditeur de gestion des stratégies de groupe, développez **configuration**de l’ordinateur, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée**sur la stratégie, puis cliquez sur **créer une stratégie**.

6.  Dans la boîte de dialogue **QoS basée** sur la stratégie, dans la page d’accueil, tapez le nom de la nouvelle stratégie dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

7.  Sur la page suivante, sélectionnez **uniquement les applications avec ce nom d’exécutable**, entrez **Lync. exe** comme nom, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie de ne classer que le trafic correspondant à partir du client Skype entreprise.

8.  Sur la troisième page, assurez-vous que **toutes les adresses IP source** et **toute adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

9.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Skype entreprise Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous avez réservé les ports 50020 via les ports 50039 pour le trafic audio, entrez la plage de ports au format suivant : **50020:50039**. Cliquez sur**Terminer**.

Une fois que vous avez créé la stratégie de qualité de service pour l’audio, vous devez créer une deuxième stratégie pour la vidéo. Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent (et unique).

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Comme indiqué précédemment, il n’est pas nécessaire d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP différente de celle utilisée pour l’audio.)

  - Utiliser la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 58000 à 58019 pour la vidéo, définissez la plage de ports comme suit : **58000:58019**.

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, procédez comme suit :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **partage d’application Skype entreprise Server**).

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Encore une fois, cette valeur ne doit pas être égale à 24 ; elle doit simplement être différente des valeurs DSCP utilisées pour l’audio et la vidéo.)

  - Utiliser la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 42000 à 42019 pour le partage d’application, définissez la plage de ports comme suit : **42000:42019**.

Pour une stratégie de transfert de fichiers :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Skype entreprise Server**).

  - Définissez la valeur DSCP sur **14**. (Encore une fois, cette valeur ne doit pas être 14 ; elle doit simplement être un code DSCP unique.)

  - Utilisez la plage de ports précédemment configurée pour l’application. Par exemple, si vous avez réservé les ports 42020 à 42039 pour le partage d’application, définissez la plage de ports comme suit : **42020:42039**.

Les nouvelles stratégies que vous avez créées ne prendront effet qu’après l’actualisation de la stratégie de groupe sur vos ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

    Gpupdate.exe /force

Cette commande peut être exécutée à partir de n’importe quelle fenêtre de commande exécutée sous les informations d’identification d’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

Gardez à l’esprit que ces stratégies doivent être ciblées vers vos ordinateurs clients. Elles ne doivent pas être appliquées aux serveurs exécutant Skype entreprise Server.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la nouvelle valeur de Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue **modifier la chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre et EBOOT votre ordinateur.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurer la qualité de service sur les ordinateurs avec plusieurs cartes réseau

Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, vous pouvez parfois rencontrer des problèmes lorsque des valeurs DSCP sont affichées sous la forme 0x00 au lieu de la valeur configurée. Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs cartes réseau ne peuvent pas accéder à votre domaine Active Directory (par exemple, si ces adaptateurs sont utilisés pour un réseau privé). Dans ce cas, les valeurs DSCP seront balisées pour les cartes qui peuvent accéder au domaine, mais elles ne seront pas balisées pour les cartes qui ne peuvent pas accéder au domaine.

Si vous souhaitez marquer les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les adaptateurs qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre. Pour cela, effectuez la procédure suivante :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.

4.  Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la nouvelle valeur de Registre créée, tapez **ne pas utiliser NLA**, puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue **modifier la chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

Après avoir créé et configuré la nouvelle valeur de Registre, vous devrez redémarrer votre ordinateur pour que les modifications prennent effet.

## <a name="see-also"></a>Voir aussi

[Créer un objet de stratégie de groupe dans Windows 10](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
