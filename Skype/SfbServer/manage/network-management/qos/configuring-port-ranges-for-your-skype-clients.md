---
title: Configuration des plages de ports et d’une stratégie de qualité de service pour vos clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cet article explique comment configurer des plages de ports pour vos clients et configurer des stratégies de qualité de service dans Skype Entreprise Server pour les clients qui s’exécutent sur Windows 10.
ms.openlocfilehash: 73bb41a2d7bb585252e8362cf70f2988c6df5882
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398918"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuration des plages de ports et d’une stratégie de qualité de service pour vos clients dans Skype Entreprise Server

Cet article explique comment configurer des plages de ports pour vos clients et configurer des stratégies de qualité de service dans Skype Entreprise Server pour les clients qui s’exécutent sur Windows 10.

## <a name="configure-port-ranges"></a>Configurer des plages de ports

Par défaut, les applications clientes Skype Entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsqu’elles sont impliquées dans une session de communication , car des plages de ports spécifiques ne sont pas automatiquement activées pour les clients. Toutefois, pour utiliser la qualité de service, vous devez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et transfert de fichiers) à une série de plages de ports uniques. Pour ce faire, vous pouvez utiliser l'Set-CsConferencingConfiguration cmdlet.

> [!NOTE]  
> Les utilisateurs finaux ne peuvent pas effectuer ces modifications eux-mêmes. Les modifications de port peuvent uniquement être apportées par les administrateurs à l’aide Set-CsConferencingConfiguration cmdlet.


Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Skype Entreprise Server Management Shell :

**Get-CsConferencingConfiguration**

En supposant que vous n’avez pas apporté de modifications à vos paramètres de conférence depuis l’installation de Skype Entreprise Server, vous devez obtenir des informations qui incluent ces valeurs de propriété :

ClientMediaPortRangeEnabled : False<br/>
ClientAudioPort : 5350<br/>
ClientAudioPortRange : 40<br/>
ClientVideoPort : 5350<br/>
ClientVideoPortRange : 40<br/>
ClientAppSharingPort : 5350<br/>
ClientAppSharingPortRange : 40<br/>
ClientFileTransferPort : 5350<br/>
ClientTransferPortRange : 40<br/>

Si vous regardez attentivement le résultat précédent, vous verrez deux choses d’importance. Tout d’abord, la propriété ClientMediaPortRangeEnabled est définie sur False :

**ClientMediaPortRangeEnabled : False**

Ceci est important car, lorsque cette propriété est définie sur False, les clients Skype Entreprise utilisent n’importe quel port disponible entre les ports 1024 et 65535 lorsqu’ils sont impliqués dans une session de communication ; cela est vrai indépendamment des autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort). Si vous souhaitez limiter l’utilisation à un ensemble spécifique de ports (et c’est une chose que vous souhaitez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de ports de média client. Pour ce faire, utilisez la commande Windows PowerShell suivante :

**Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

La commande précédente active les plages de ports de média client pour la collection globale de paramètres de configuration de conférence ; toutefois, ces paramètres peuvent également être appliqués à l’étendue Site et/ou Service (pour le service Serveur de conférence uniquement). Pour activer les plages de ports de média client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration :

**Set-CsConferencingConfiguration -Identity « site:Redmond » -ClientMediaPortRangeEnabled $True**

Vous pouvez également utiliser cette commande pour activer simultanément des plages de ports pour tous vos paramètres de configuration de conférence :

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

La deuxième chose importante que vous remarquerez est que l’exemple de sortie montre que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques :

ClientAudioPort : 5350<br/>
ClientVideoPort : 5350<br/>
ClientAppSharingPort : 5350<br/>
ClientFileTransferPort : 5350<br/>

Pour implémenter QoS, chacune de ces plages de ports doit être unique. Par exemple, vous pouvez configurer les plages de ports comme ceci :


<table>
<colgroup>
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
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurées pour vos serveurs. Par exemple, sur les serveurs, le partage d’application a été configuré pour utiliser les ports 40803 à 49151 ; sur les ordinateurs clients, le partage d’application est configuré pour utiliser les ports 42000 à 42019. Cette tâche est également effectuée principalement pour faciliter l’administration de la qualité de service : les ports clients n’ont pas besoin de représenter un sous-ensemble des ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application pour utiliser, par exemple, les ports 10000 à 10019.) Toutefois, il est recommandé de faire de vos plages de ports client un sous-ensemble de vos plages de ports de serveur.

En outre, vous avez peut-être remarqué que 8 348 ports ont été mis de côté pour le partage d’application sur les serveurs, mais que seuls 20 ports ont été mis de côté pour le partage d’application sur les clients. Cela est également recommandé, mais il ne s’agit pas d’une règle difficile et rapide. En règle générale, vous pouvez considérer chaque port disponible pour représenter une seule session de communication : si vous avez 100 ports disponibles dans une plage de ports, cela signifie que l’ordinateur en question peut participer, au maximum, à 100 sessions de communication à un moment donné. Étant donné que les serveurs participeront probablement à beaucoup plus de conversations que de clients, il est logique d’ouvrir beaucoup plus de ports sur les serveurs que sur les clients. La définition de 20 ports pour le partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, et le tout en même temps. Cela devrait s’avérer suffisant pour la grande majorité de vos utilisateurs.

Pour affecter les plages de ports précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande Skype Entreprise Server Management Shell suivante :

**Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

Vous pouvez également utiliser cette commande pour affecter ces mêmes plages de ports pour tous vos paramètres de configuration de conférence :

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

Les utilisateurs individuels doivent se déconnecter Skype Entreprise puis se déconnecter pour que ces modifications prennent effet.

> [!NOTE]  
> Vous pouvez également activer les plages de ports de média client, puis les affecter à l’aide d’une seule commande. Par exemple :<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurer des stratégies de qualité de service pour les clients qui s’exécutent sur Windows 10

En plus de spécifier des plages de ports à utiliser par vos clients Skype Entreprise, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients. (Les stratégies de qualité de service créées pour les serveurs de conférence, d’application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant Skype Entreprise client et Windows 10.

L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :


<table>
<colgroup>
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
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

Pour créer une stratégie audio de qualité de service pour Windows 10, connectez-vous d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez la gestion des stratégies de groupe **(cliquez sur** Démarrer, pointez sur Outils d’administration **, puis** cliquez sur **Gestion** des stratégies de groupe), puis complétez la procédure suivante :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une ou plusieurs de vos clients, la nouvelle stratégie doit être créée dans l’ou client.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un **GPO dans ce domaine, puis le lier ici**.

3.  Dans la **boîte de dialogue Nouvel objet** de stratégie de groupe, tapez un nom pour le nouvel  objet de stratégie de groupe dans la zone Nom, puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.

5.  Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration** ordinateur, **développez Windows Paramètres**, cliquez avec le bouton droit sur **QoS** basé sur la stratégie, puis cliquez sur Créer **une stratégie**.

6.  Dans la **boîte de dialogue QoS** basée sur la stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la **zone** Nom. Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

7.  Sur la page suivante, sélectionnez **Uniquement les applications** avec ce nom exécutable, entrez **Lync.exe** comme nom, puis cliquez sur **Suivant**. Ce paramètre indique à la stratégie de hiérarchiser uniquement le trafic correspondant à partir Skype Entreprise client.

8.  Dans la troisième page, assurez-vous que les adresses **IP source Any** et **Any destination** sont sélectionnées, puis cliquez sur **Suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

9.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Skype Entreprise Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous avez réservé les ports 50020 à 50039 pour le trafic audio, entrez la plage de ports en utilisant ce format : **50020:50039**. Cliquez sur **Terminer**.

Après avoir créé la stratégie QoS pour l’audio, vous devez créer une deuxième stratégie pour la vidéo. Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent (et unique).

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Comme indiqué précédemment, vous n’avez pas besoin d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP différente de celle utilisée pour l’audio.)

  - Utilisez la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 58000 à 58019 pour la vidéo, définissez la plage de ports comme ceci : **58000:58019**.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, faites les substitutions ci-après :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server partage d’application**).

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, cette valeur ne doit pas être 24 ; elle doit simplement être différente des valeurs DSCP utilisées pour l’audio et la vidéo.)

  - Utilisez la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 42000 à 42019 pour le partage d’application, définissez la plage de ports comme ceci : **42000:42019**.

Pour une stratégie de transfert de fichiers :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server transferts de fichiers**).

  - Définissez la valeur DSCP sur **14**. (Là encore, cette valeur ne doit pas être 14 ; il doit simplement s’agit d’un code DSCP unique.)

  - Utilisez la plage de ports configurée précédemment pour l’application. Par exemple, si vous avez réservé les ports 42020 à 42039 pour le partage d’application, définissez la plage de ports comme ceci : **42020:42039**.

Les nouvelles stratégies que vous avez créées ne prennent effet qu’une fois la stratégie de groupe actualisée sur vos ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

**Gpupdate.exe /force**

Cette commande peut être exécuté à partir de n’importe quelle fenêtre de commande qui s’exécute sous les informations d’identification de l’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

Gardez à l’esprit que ces stratégies doivent être ciblées sur vos ordinateurs clients. Elles ne doivent pas être appliquées aux serveurs exécutant Skype Entreprise Server.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la **boîte de** dialogue Exécuter, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEYLOCALMACHINE\_\_**, **DÉVELOPPEZ SYSTEM**, **CurrentControlSet**, développez **les services**, puis **développez Tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA**, puis appuyez sur Entrée pour renommer la valeur.

6.  Double-cliquez **sur Ne pas utiliser le NLA**. Dans la **boîte de dialogue Modifier la** chaîne, tapez **1** dans la zone Données de la valeur, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et redémarrez votre ordinateur.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurer la qualité de service sur des ordinateurs avec plusieurs cartes réseau

Si vous disposez d’un ordinateur qui possède plusieurs cartes réseau, vous pouvez parfois vous exécuter dans des problèmes où les valeurs DSCP sont affichées en tant que 0x00 plutôt que la valeur configurée. Cela se produit généralement sur les ordinateurs sur lequel une ou plusieurs cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé). Dans ce cas, les valeurs DSCP sont marquées pour les adaptateurs qui peuvent accéder au domaine, mais pas pour les adaptateurs qui ne peuvent pas accéder au domaine.

Si vous souhaitez baliser des valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le Registre. Pour cela, effectuez la procédure suivante :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la **boîte de** dialogue Exécuter, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEYLOCALMACHINE\_\_**, **DÉVELOPPEZ SYSTEM**, **CurrentControlSet**, développez **les services**, puis **développez Tcpip**.

4.  Si vous ne voyez pas de clé de Registre étiquetée **QoS** , cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA**, puis appuyez sur Entrée pour renommer la valeur.

6.  Double-cliquez **sur Ne pas utiliser le NLA**. Dans la **boîte de dialogue Modifier la** chaîne, tapez **1** dans la zone Données de la valeur, puis cliquez sur **OK**.

Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur pour que les modifications prennent effet.

## <a name="see-also"></a>Voir aussi

[Créer un objet de stratégie de groupe dans Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
