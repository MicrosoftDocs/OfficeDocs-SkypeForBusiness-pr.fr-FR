---
title: Configuration des plages de ports et d’une qualité de service pour vos serveurs Edge
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cet article explique comment configurer des plages de ports pour les serveurs Edge et comment configurer une stratégie de qualité de service pour vos serveurs Edge A/V.
ms.openlocfilehash: ae955eb8863f561cc1837b7f0319f7424f13e99c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829938"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs Edge dans Skype Entreprise Server

Cet article explique comment configurer des plages de ports pour les serveurs Edge et comment configurer une stratégie de qualité de service pour vos serveurs Edge A/V.

## <a name="configure-port-ranges"></a>Configurer des plages de ports

Avec les serveurs Edge, vous n’avez pas besoin de configurer des plages de ports distinctes pour l’audio, la vidéo et le partage d’application . De même, les plages de ports utilisées pour les serveurs Edge n’ont pas besoin de correspondre aux plages de ports utilisées avec vos serveurs de conférence, d’application et de médiation. Avant de poursuivre notre exemple, il est important de souligner que même si cette option existe, nous vous recommandons de ne pas modifier les plages de ports, car cela peut nuire à certains scénarios si vous vous déplacez hors de la plage de ports 50000.

Par exemple, supposons que vous ayez configuré vos serveurs de conférence, d’applications et de médiation afin d’utiliser ces plages de ports :


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Type de paquet</th>
<th>Port de début</th>
<th>Nombre de ports réservés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Partage d’application</p></td>
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


Comme vous pouvez le voir, vos plages de ports pour l’audio, la vidéo et le partage d’application commencent au port 40803 et englobent un total de 24 732 ports. Si vous préférez, vous pouvez configurer un serveur Edge donné pour utiliser ces valeurs de port globales en exécutant une commande semblable à celle-ci à partir de l’Skype Entreprise Server Management Shell :

  **Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730**

Ou utilisez la commande suivante pour configurer simultanément tous les serveurs Edge de votre organisation :

  **Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_. Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}**

Vous pouvez vérifier les paramètres de port actuels de vos serveurs Edge à l’aide de la commande Skype Entreprise Server Management Shell :

  **Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount**

Là encore, bien que nous fournissions ces options, nous vous recommandons vivement de laisser les éléments tels qu’ils sont pour la configuration du port.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurer une stratégie QoS pour vos serveurs Edge A/V

En plus de créer des stratégies de QoS pour vos serveurs de conférence, d’application et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs Edge A/V. Toutefois, les stratégies utilisées sur vos serveurs Edge sont différentes des stratégies utilisées sur vos serveurs de conférence, d’application et de médiation. Pour les serveurs de conférence, d’application et de médiation, vous avez spécifié une plage de ports source ; avec les serveurs Edge, vous devez spécifier une plage de ports de destination. Pour cette raison, vous ne pouvez pas simplement appliquer les stratégies de qualité de service de conférence, d’application et de serveur de médiation à vos serveurs Edge : ces stratégies ne fonctionneront tout simplement pas. Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer ces stratégies à vos serveurs Edge uniquement.

La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisés pour gérer la qualité de service sur les serveurs Edge. Bien entendu, il est possible que vos serveurs Edge soient des serveurs autonomes qui n’ont pas de compte Active Directory. Si c’est le cas, vous pouvez utiliser la stratégie de groupe locale au lieu de la stratégie de groupe Active Directory : la seule différence est que vous devez créer ces stratégies locales à l’aide de l’Éditeur de stratégie de groupe local et créer individuellement le même ensemble de stratégies sur chaque serveur Edge. Pour démarrer l’Éditeur de stratégie de groupe locale sur un serveur Edge, vous pouvez :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la **boîte de** dialogue Exécuter, **tapez gpedit.msc,** puis appuyez sur Entrée.

Si vous créez des stratégies basées sur Active Directory, vous devez vous connecter à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Dans ce cas, ouvrez la gestion des stratégies de groupe (cliquez sur **Démarrer,** pointez sur Outils d’administration, puis cliquez sur Gestion des stratégies de **groupe),** puis complétez les étapes suivantes :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs Skype Entreprise Server sont situés dans une ou plusieurs Skype Entreprise Server, la nouvelle stratégie doit être créée dans l’Skype Entreprise Server’une autre.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un GPO dans ce domaine, puis le **lier ici.**

3.  Dans la **boîte** de dialogue Nouvel objet de stratégie de  groupe, tapez un nom pour le nouvel objet de stratégie de groupe dans la zone Nom (par exemple, **Skype Entreprise Server Audio),** puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier.**

À partir de là, le processus est identique, que vous créiez une stratégie Active Directory ou une stratégie locale :

1.  Dans l’Éditeur de gestion des stratégies de groupe ou l’Éditeur de stratégie de groupe local, développez **Configuration** ordinateur, Développez Stratégies,  **développez Windows Paramètres**, cliquez avec le bouton droit sur **QoS** basé sur la stratégie, puis cliquez sur Créer une **stratégie.**

2.  Dans la boîte de dialogue **QoS** basée sur la stratégie, sur la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **Skype Entreprise Server Audio**) dans la zone **Nom.** Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

3.  Sur la page suivante, assurez-vous que toutes les **applications** sont sélectionnées, puis cliquez sur **Suivant**. Ce paramètre indique au réseau de rechercher tous les paquets avec un marquage DSCP de 46, et pas seulement les paquets créés par une application spécifique.

4.  Sur la troisième page, assurez-vous que les adresses **IP source Et** Toute adresse IP de **destination** sont sélectionnées, puis cliquez sur **Suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

5.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Skype Entreprise Server et ses applications clientes.

6.  Sous le titre **Spécifiez le numéro de port de destination,** **sélectionnez À partir de ce port ou plage de destination.** Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous avez réservé les ports 49152 à 57500 pour le trafic audio, entrez la plage de ports en utilisant ce format : **49152:57500**. Cliquez sur **Terminer**.

Après avoir créé la stratégie QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo. Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server Vidéo).**

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).

  - Utilisez la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports sur celle-ci : **57501:65535**. Là encore, il doit être configuré comme plage de ports de destination.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie, en faisant les substitutions suivantes :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server partage d’application).**

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).

  - Utilisez la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.

Les nouvelles stratégies que vous avez créées ne prennent effet qu’une fois la stratégie de groupe actualisée sur vos serveurs Edge. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

 **Gpudate.exe /force**

Cette commande peut être exécuté à partir de l’Skype Entreprise Server ou de toute fenêtre de commande qui s’exécute sous les informations d’identification de l’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Notez que vous devrez peut-être redémarrer le serveur Edge même après avoir Gpudate.exe.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la **boîte de** dialogue Exécuter, tapez **regedit,** puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEY \_ LOCAL \_ MACHINE,** développez **SYSTEM,** **CurrentControlSet,** développez **les services,** puis **développez Tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS,** puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA,** puis appuyez sur Entrée pour renommer la valeur.

6.  Double-cliquez sur **Ne pas utiliser NLA**. Dans la boîte **de dialogue Modifier**  la chaîne, tapez **1** dans la zone de données Valeur, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et redémarrez votre ordinateur.
