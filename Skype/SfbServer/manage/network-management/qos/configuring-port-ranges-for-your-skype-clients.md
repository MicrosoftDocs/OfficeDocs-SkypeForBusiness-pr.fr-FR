---
title: Configuration des plages de ports et une stratégie de qualité de Service pour vos clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article explique comment configurer les plages de ports pour vos clients et la configuration des stratégies de qualité de Service dans Skype pour Business Server pour les clients s’exécutant sur Windows 10.
ms.openlocfilehash: 9377274b625af7a4ed93b46a0f6a741e89eee1eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913068"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuration des plages de ports et d’une stratégie de qualité de Service pour vos clients dans Skype pour Business Server

Cet article explique comment configurer les plages de ports pour vos clients et la configuration des stratégies de qualité de Service dans Skype pour Business Server pour les clients s’exécutant sur Windows 10.

## <a name="configure-port-ranges"></a>Configurer les plages de ports

Par défaut, le Skype pour les applications client d’entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsque impliquées dans une session de communication ; Il s’agit, car les plages de ports ne sont pas automatiquement activés pour les clients. Pour pouvoir utiliser la qualité de Service, toutefois, vous devrez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et le transfert de fichiers) à une série de plages de ports uniques. Cette opération peut être effectuée à l’aide de l’applet de commande Set-CsConferencingConfiguration.

> [!NOTE]  
> Les utilisateurs finaux ne peuvent pas apporter ces modifications eux-mêmes. Modifications de port ne peuvent être effectuées par les administrateurs à l’aide de l’applet de commande Set-CsConferencingConfiguration.


Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de la Skype pour Business Server Management Shell :

    Get-CsConferencingConfiguration

En supposant que vous n’avez apporté des modifications à vos paramètres de conférence dans la mesure où vous avez installé Skype pour Business Server, vous devriez obtenir des informations comprenant ces valeurs de propriété :

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si vous examinez attentivement la sortie précédente, vous verrez deux choses d’importance. Tout d’abord, la propriété de paramètres ClientMediaPortRangeEnabled est définie sur False :

    ClientMediaPortRangeEnabled : False

Ceci est important car, lorsque cette propriété est définie sur False, Skype pour les clients professionnels utilisent n’importe quel port disponible entre les ports 1024 et 65535 lorsque impliquées dans une session de communication ; Cela est vrai indépendamment des autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort). Si vous souhaitez limiter l’utilisation à un ensemble de ports spécifié (et il s’agit d’un élément que vous ne souhaitez pas faire si vous envisagez l’implémentation de qualité de Service), vous devez tout d’abord activer plages de ports multimédia client. Qui peut être effectuée à l’aide de la commande Windows PowerShell suivante :

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

La commande précédente Active les plages de ports multimédia client pour la collection globale des paramètres de configuration de conférence ; Toutefois, ces paramètres peuvent également s’appliquer à l’étendue site et/ou l’étendue service (pour le service de serveur de conférence). Pour activer le média client port plages pour un site spécifique ou un serveur, spécifiez l’identité du site ou du serveur lors de l’appel de Set-CsConferencingConfiguration :

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Vous pouvez également utiliser cette commande pour activer simultanément des plages de ports pour tous vos paramètres de configuration de conférence :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La deuxième chose importante à remarquer est que la sortie d’exemple montre que, par défaut, les ports multimédias plages définies pour chaque type de trafic réseau est identiques :

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Pour mettre en œuvre QoS, chacune de ces plages de ports vous devrez être uniques. Par exemple, vous pouvez configurer les plages de ports comme suit :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Port de début</th>
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


Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurée pour vos serveurs. Par exemple, sur les serveurs, partage d’application a été configuré pour utiliser des ports 40803 via et 49 151 ; sur les ordinateurs clients, partage d’application est configuré pour utiliser des ports 42000 via 42019. Trop, cela principalement pour faciliter l’administration de QoS : ports client n’ont pas représenter un sous-ensemble des ports utilisés sur le serveur. (Par exemple, sur les ordinateurs clients vous pouvez configurer partage d’application pour utiliser, par exemple, ports 10000 par le biais de 10019.) Toutefois, il est recommandé que vous apportez à votre client de plages de ports un sous-ensemble des plages de ports votre serveur.

En outre, vous avez sans doute remarqué que 8348 ports ont été attribuées au partage d’application sur les serveurs, mais que 20 ports ont été attribuées au partage d’application sur les clients. Cela trop, est recommandé, mais n’est pas une règle absolue. En règle générale, vous pouvez considérer chaque port disponible pour représenter une session de communication unique : Si vous avez 100 ports disponibles dans une plage de ports, ce qui signifie que l’ordinateur en question peut participer, au maximum 100 sessions de communication à tout moment donné. Étant donné que les serveurs seront probablement prendre part à des conversations plus nombreux que les clients, c’est significatif pour ouvrir des ports plus nombreux sur les serveurs que sur les clients. Paramètre côté 20 ports partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur le périphérique spécifié et tous en même temps. Qui doit s’avérer suffisant pour la plupart de vos utilisateurs.

Pour affecter les plages de ports précédentes à votre collection globale des paramètres de configuration de conférence, vous pouvez utiliser le suivant Skype de commande Business Server Management Shell :

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Ou bien, utilisez cette commande pour affecter ces mêmes plages de ports pour toutes les conférences de vos paramètres de configuration :

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Des utilisateurs individuels doivent se déconnecter de Skype pour les entreprises et se reconnecter avant que ces modifications puissent prendre effet.

> [!NOTE]  
> Vous pouvez également activer les plages de ports multimédia client et ensuite affecter ces plages de ports, à l’aide d’une seule commande. Par exemple :<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configuration des stratégies de qualité de Service de clients s’exécutant sur Windows 10

Outre la spécification des plages de ports pour une utilisation par votre Skype pour les clients d’entreprise, vous devez également créer des stratégies de qualité de Service distincts qui seront appliqués aux ordinateurs clients. (Les stratégies de qualité de Service créées pour les serveurs de conférence, d’Application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’applique uniquement aux ordinateurs qui exécutent le Skype pour client d’entreprise et 10 Windows.

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
<th>Port de début</th>
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

Pour créer une stratégie audio de qualité de Service pour les ordinateurs Windows 10, ouvrez une session un ordinateur où la gestion des stratégies de groupe a été installée. Ouvrez Gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestion des stratégies de groupe**), puis effectuez la procédure suivante :

1.  Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée Clients, la nouvelle stratégie doit être créée en l’unité d’organisation du Client.

2.  Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.

3.  Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

4.  Avec le bouton droit de la stratégie créée, puis cliquez sur **Modifier**.

5.  Dans l’éditeur de gestion de stratégie de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**. Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.

7.  Dans la page suivante, vérifiez que **toutes les applications** est sélectionné, puis cliquez sur **suivant**. Ce paramètre indique le réseau pour rechercher tous les paquets avec un marquage DSCP des paquets pas seulement 46, créé par une application spécifique.

8.  Dans la troisième page, assurez-vous que **toute adresse IP source** et **n’importe quelle adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**. Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.

9.  Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau plus couramment utilisés par Skype pour Business Server et ses applications clientes.

10. Sous le titre, **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port source ou de la plage**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservé ports 50020 par le biais des ports 50039 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **50020:50039**. Cliquez sur **Terminer**.

Après avoir créé la stratégie QoS pour l’audio, vous devez ensuite créer une deuxième stratégie pour la vidéo. Pour créer une stratégie pour la vidéo, suivez la même procédure de base que vous avez suivi lors de la création de la stratégie audio, effectuant les substitutions :

  - Utilisez un nom de stratégie différent (et unique).

  - Définissez la valeur DSCP **34** au lieu de 46. (Comme mentionné précédemment, il est inutile d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP autre que celui utilisé pour l’audio).

  - Utiliser la plage de ports précédemment configuré pour le trafic vidéo. Par exemple, si vous avez réservé ports 58000 via 58019 pour la vidéo, définissez la plage de ports à ceci : **58000:58019**.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, effectuez les remplacements suivants :

  - Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour le partage d’Application Business Server**).

  - Définissez la valeur DSCP à **24** au lieu de 46. (Là encore, cette valeur ne doit pas être 24 ; il doit simplement être différent dans les valeurs DSCP utilisés pour l’audio et vidéo).

  - Utiliser la plage de ports précédemment configuré pour le trafic vidéo. Par exemple, si vous avez réservé ports 42000 par le biais de 42019 pour le partage d’application, définissez la plage de ports à ceci : **42000:42019**.

Pour une stratégie de transfert de fichier :

  - Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour les transferts de fichiers Business Server**).

  - Définissez la valeur DSCP **14**. (Là encore, cette valeur ne doit pas être 14 ; il doit simplement être un code DSCP unique).

  - Utiliser la plage de ports précédemment configuré pour l’application. Par exemple, si vous avez réservé ports 42020 par le biais de 42039 pour le partage d’application, définissez la plage de ports à ceci : **42020:42039**.

Les nouvelles stratégies que vous avez créé ne prendra pas effet tant que la stratégie de groupe a été actualisée sur vos ordinateurs clients. Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur où la stratégie de groupe doivent être actualisées :

    Gpudate.exe /force

Cette commande peut être exécutée à partir de n’importe quelle fenêtre de commande s’exécutant sous les informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez sur **invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

N’oubliez pas que ces stratégies doivent être ciblés vers vos ordinateurs clients. Ils ne doivent pas être appliquées à des serveurs exécutant Skype pour Business Server.

Pour garantir que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en procédant comme suit :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_ordinateur**, développez **système**, développez **CurrentControlSet**, développez **services**et **puis TCPIP**.

4.  Cliquez sur **TCP/IP**, pointez sur **Nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre est créée, tapez **QoS**, puis appuyez sur ENTRÉE pour renommer la clé.

5.  Avec le bouton droit **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**. Une fois la nouvelle valeur de Registre est créée, tapez **n’utilisez pas l’authentification réseau**, puis appuyez sur ENTRÉE pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser l’authentification réseau**. Dans la boîte de dialogue **Modification de la chaîne** , tapez **1** dans la zone **valeur** , puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et eboot votre ordinateur.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurer la qualité de Service sur des ordinateurs ayant plusieurs cartes réseau

Si vous disposez d’un ordinateur qui possède plusieurs cartes réseau, vous pouvez exécuter occasionnellement problèmes où les valeurs DSCP sont affichés sous forme de 0 x 00 plutôt que la valeur configurée. Cela se produit généralement sur les ordinateurs où un ou plusieurs des cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé). Dans ce cas qui, valeurs DSCP seront balisés pour les cartes réseau qui peuvent accéder au domaine, mais ne seront pas balisés pour les cartes qui ne peuvent pas accéder au domaine.

Si vous souhaitez les valeurs DSCP balise pour toutes les cartes réseau sur un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le Registre. Qui peuvent être effectuées en procédant comme suit :

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_ordinateur**, développez **système**, développez **CurrentControlSet**, développez **services**et **puis TCPIP**.

4.  Si vous ne voyez pas d’une clé de Registre intitulée **QoS** puis **Tcpip**d’avec le bouton droit, pointez sur **Nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur ENTRÉE pour renommer la clé.

5.  Avec le bouton droit **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**. Une fois la nouvelle valeur de Registre est créée, tapez **n’utilisez pas l’authentification réseau**, puis appuyez sur ENTRÉE pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser l’authentification réseau**. Dans la boîte de dialogue **Modification de la chaîne** , tapez **1** dans la zone **valeur** , puis cliquez sur **OK**.

Après la création et la configuration de la nouvelle valeur de Registre, vous devrez redémarrer votre ordinateur pour que les modifications prennent effet.

## <a name="see-also"></a>Voir aussi

[Créer un objet de stratégie de groupe dans Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
