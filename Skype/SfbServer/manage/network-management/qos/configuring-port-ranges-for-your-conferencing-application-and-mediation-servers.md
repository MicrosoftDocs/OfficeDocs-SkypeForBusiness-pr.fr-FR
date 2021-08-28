---
title: Configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cet article explique comment configurer des plages de ports et une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation.
ms.openlocfilehash: 6e5b420b4ccc8cc59a45834cbd898ccc5b2ec180
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634288"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation

Cet article explique comment configurer des plages de ports et une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation.

## <a name="configure-port-ranges"></a>Configurer des plages de ports

Pour implémenter la qualité de service, vous devez configurer des plages de ports identiques pour le partage audio, vidéo et d’application sur vos serveurs de conférence, d’application et de médiation. en outre, ces plages de ports ne doivent pas se chevaucher. Pour utiliser un exemple simple, supposons que vous utilisez les ports 10000 à 10999 pour la vidéo sur vos serveurs de conférence. Cela signifie que vous devez également réserver les ports 10000 à 10999 pour la vidéo sur vos serveurs d’applications et de médiation. Si vous ne le faites pas, QoS ne fonctionne pas comme prévu.

De même, supposons que vous réserviez les ports 10000 à 10999 pour la vidéo mais que vous réserviez ensuite les ports 10500 à 11999 pour l’audio. Cela peut créer des problèmes de qualité de service, car les plages de ports se chevauchent. Avec QoS, chaque modalité doit avoir un ensemble unique de ports : si vous utilisez les ports 10000 à 10999 pour la vidéo, vous devez utiliser une plage différente (par exemple, 11000 à 11999, pour l’audio).

Par défaut, les plages de ports audio et vidéo ne se chevauchent pas Skype Entreprise Server ; toutefois, les plages de ports affectées au partage d’application se chevauchent avec les plages de ports audio et vidéo. (Ce qui signifie, à son tour, qu’aucune de ces plages n’est unique.) Vous pouvez vérifier les plages de ports existantes pour vos serveurs de conférence, d’application et de médiation en exécutant les trois commandes suivantes à partir de l’Skype Entreprise Server Management Shell :

  Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
  Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
  Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Comme vous pouvez le voir dans les commandes précédentes, chaque type de port (audio, vidéo et partage d’application) se voit attribuer deux valeurs de propriété distinctes : le début du port et le nombre de ports. Le début du port indique le premier port utilisé pour cette modalité ; par exemple, si le début du port audio est égal à 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000. Si le nombre de ports audio est 2 (ce qui n’est pas une valeur valide, mais est utilisé ici à des fins d’illustration), cela signifie que seuls deux ports sont alloués à l’audio. Si le premier port est le port 50000 et qu’il y a au total deux ports, cela signifie que le deuxième port doit être le port 50001 (les plages de ports doivent être contiguës). Par conséquent, la plage de ports pour l’audio serait de 50000 à 50001, inclus.<BR><br>Notez également que le serveur d’applications et le serveur de médiation ne prennent en charge la qualité de service que pour l’audio. Vous n’avez pas besoin de modifier les ports vidéo ou de partage d’application sur vos serveurs d’applications ou vos serveurs de médiation.

Si vous exécutez les trois commandes précédentes, vous verrez que les valeurs de port par défaut pour Skype Entreprise Server sont configurées comme ceci :

<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Propriété</th>
<th>Serveur de conférence</th>
<th>Serveur d’applications</th>
<th>Serveur de médiation</th>
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

Comme indiqué précédemment, lors de la configuration de ports Skype Entreprise Server pour QoS, vous devez vous assurer que : 1) les paramètres de port audio sont identiques sur vos serveurs de conférence, d’application et de médiation . et, 2) les plages de ports ne se chevauchent pas. Si vous examinez attentivement le tableau précédent, vous voyez que les plages de ports sont identiques sur les trois types de serveur. Par exemple, le port audio de début est fixé au port 49152 sur chaque type de serveur et le nombre total de ports réservés à l’audio sur chaque serveur est également identique : 8 348. Toutefois, les plages de ports se chevauchent : les ports audio débutent au port 49152 mais c’est le cas également pour les ports réservés au partage d’application. Pour permettre une qualité de service optimale, le partage d’application doit être reconfiguré afin d’utiliser une plage de ports unique. Par exemple, vous pouvez configurer le partage d’application pour démarrer au port 40803 et utiliser 8 348 ports. Pourquoi 8 348 ports ? Si vous ajoutez ces valeurs ensemble (40803 + 8348), cela signifie que le partage d’application utilisera les ports 40803 à 49150. Comme les ports audio ne commencent pas avant le port 49152, vous n’avez plus de plages de ports qui se chevauchent.

Une fois que vous avez sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez apporter vos changements à l’aide de lSet-CsConferencingServer cmdlet. Cette modification n’a pas à être effectuée sur vos serveurs d’applications ou vos serveurs de médiation, car ces serveurs ne gèrent pas le trafic du partage d’application. Vous ne devez changer les valeurs de ports de ces serveurs que si vous décidez de réaffecter les ports utilisés pour le trafic audio.

Pour modifier les valeurs de port pour le partage d’application sur un serveur de conférence unique, exécutez une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :

  **Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348**

Si vous souhaitez apporter ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place :

  **Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_. Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}**

Après avoir changé les paramètres de port, vous devez arrêter, puis redémarrer chaque service affecté par les modifications.

Il n’est pas obligatoire que vos serveurs de conférence, serveurs d’applications et serveurs de médiation partagent la même plage de ports. Le seul impératif est de réserver les plages de ports uniques sur tous vos serveurs. Toutefois, l’administration est généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurer une stratégie de qualité de service dans Skype Entreprise Server pour vos serveurs de conférence, d’application et de médiation

La configuration de plages de ports facilite l’utilisation de la qualité de service en s’assurant que tout le trafic d’un type donné (par exemple, tout le trafic audio) passe par le même ensemble de ports. Cela permet au système d’identifier et de marquer facilement un paquet donné : si le port 49152 est réservé au trafic audio, les paquets qui passent par le port 49152 peuvent être marqués avec un code DSCP qui indique qu’il s’agit d’un paquet audio. Cela permet aux routeurs d’identifier le paquet comme étant un paquet audio, et de lui donner une priorité supérieure aux paquets non marqués (par exemple les paquets utilisés pour copier un fichier d’un serveur sur un autre).

Cependant, la limitation d’un ensemble de ports à un type de trafic spécifique ne permet pas que ces paquets soient automatiquement marqués avec le code DSCP approprié. En plus de définir des plages de ports, vous devez également créer des stratégies de qualité de service qui spécifient le code DSCP à associer à chaque plage de ports. Par Skype Entreprise Server, cela signifie généralement la création de deux stratégies : une pour l’audio et une pour la vidéo.

Les stratégies de qualité de service sont plus faciles à créer et à gérer à l’aide de la stratégie de groupe. (Ces stratégies peuvent également être créées à l’aide de stratégies de sécurité locales. Toutefois, vous devez répéter la même procédure sur chaque ordinateur.) Votre ensemble initial de stratégies QoS (une pour l’audio et l’autre pour la vidéo) doit être appliqué uniquement aux ordinateurs Skype Entreprise Server exécutant le serveur de conférence, le serveur d’applications et/ou les services serveur de médiation. Si tous ces ordinateurs se trouvent dans la même ouo Active Directory, vous pouvez simplement affecter le nouvel objet de stratégie de groupe (GPO) à cette ou. Vous pouvez également procéder d’une autre façon pour cibler les ordinateurs spécifiés avec cette stratégie ; par exemple, vous pouvez placer les ordinateurs dans un groupe de sécurité, puis utiliser le filtrage de sécurité de la stratégie de groupe pour appliquer l’objet de stratégie de groupe uniquement à ce groupe de sécurité.

Pour créer une stratégie de qualité de service pour la gestion de l’audio, connectez-vous à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez la gestion des stratégies de groupe (cliquez sur **Démarrer,** pointez sur Outils d’administration, puis cliquez sur Gestion des stratégies de **groupe),** puis complétez la procédure suivante :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs Skype Entreprise Server sont situés dans une ou plusieurs Skype Entreprise Server, la nouvelle stratégie doit être créée dans l’Skype Entreprise Server’une autre.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un GPO dans ce domaine, puis le **lier ici.**

3.  Dans la **boîte** de dialogue Nouvel objet de stratégie de  groupe, tapez un nom pour le nouvel objet de stratégie de groupe dans la zone Nom (par exemple, **Skype Entreprise Server QoS),** puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier.**

5.  Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **Stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur la stratégie**, puis cliquez sur **Créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS** basée sur la stratégie, dans la page d’ouverture, tapez un  nom pour la nouvelle stratégie (par exemple, **Skype Entreprise Server QoS**) dans la zone Nom. Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

7.  Sur la page suivante, assurez-vous que toutes les **applications** sont sélectionnées, puis cliquez sur **Suivant**. Cela permet de s’assurer que toutes les applications feront correspondre les paquets de la plage de ports spécifiée au code DSCP correct.

8.  Sur la troisième page, assurez-vous que les adresses **IP source Et** Toute adresse IP de destination sont sélectionnées, puis cliquez sur **Suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

9.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Skype Entreprise Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous avez réservé les ports 49152 à 57500 pour le trafic audio, entrez la plage de ports en utilisant ce format : **49152:57500**. Cliquez sur **Terminer**.

> [!NOTE]  
> La valeur DSCP 46 est arbitraire : bien que DSCP 46 soit souvent utilisé pour marquer les paquets audio, vous n’êtes pas obligé d’utiliser cette valeur pour les communications audio. Si vous avez déjà implémenté QoS et que vous utilisez un autre code DSCP pour l’audio (par exemple, DSCP 40), vous devez configurer votre stratégie de qualité de service pour utiliser ce même code (c’est-à-dire, 40 pour l’audio). Si vous implémentez la qualité de service, alors il est recommandé d’utiliser DSCP 46 pour l’audio, car cette valeur est utilisée en général pour marquer les paquets audio.

Après avoir créé la stratégie QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo (et éventuellement une troisième stratégie pour la gestion du trafic de partage d’application). Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server Vidéo).**

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).

  - Utilisez la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports sur celle-ci : **57501:65535**.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie, en faisant les substitutions suivantes :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Skype Entreprise Server partage d’application).**

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).

  - Utilisez la plage de ports précédemment configurée pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.

Les nouvelles stratégies que vous avez créées ne prennent effet qu’une fois la stratégie de groupe actualisée sur Skype Entreprise Server ordinateurs. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

  **Gpupdate.exe /force**

Cette commande peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou de toute fenêtre de commande qui s’exécute sous les informations d’identification de l’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

Pour vérifier que les nouvelles stratégies QoS ont été appliquées, procédez ainsi :

1.  Sur un Skype Entreprise Server, cliquez sur **Démarrer,** puis sur **Exécuter.**

2.  Dans la **boîte de** dialogue Exécuter, tapez **regedit,** puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **Ordinateur,** développez **HKEY \_ LOCAL \_ MACHINE,** développez **SOFTWARE,** développez **Stratégies,** **développez Microsoft,** développez **Windows,** puis cliquez sur **QoS**. Sous **QoS** des clés de registre pour chaque stratégie QoS créée doivent s’afficher. Par exemple, si vous avez créé deux nouvelles stratégies (l’une nommée Skype Entreprise Server Audio QoS et l’autre appelée Skype Entreprise Server Video QoS), vous devriez voir des entrées de Registre pour la qualité de service audio Skype Entreprise Server et la qualité de service Skype Entreprise Server Video.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la **boîte de** dialogue Exécuter, tapez **regedit,** puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEY \_ LOCAL \_ MACHINE,** développez **SYSTEM,** **CurrentControlSet,** développez **les services,** puis **développez Tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS,** puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA,** puis appuyez sur Entrée pour renommer la valeur.

6.  Double-cliquez **sur Ne pas utiliser le NLA**. Dans la boîte **de dialogue Modifier**  la chaîne, tapez **1** dans la zone de données Valeur, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et redémarrez votre ordinateur.
