---
title: Installation et configuration de nœuds observateurs
TOCTitle: Installation et configuration de nœuds observateurs
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204943(v=OCS.15)
ms:contentKeyID: 49297387
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation et configuration de nœuds observateurs

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les *nœuds observateur* sont des ordinateurs qui exécutent périodiquement des transactions synthétiques Lync Server. Les *transactions synthétiques* sont des applets de commande Windows PowerShell qui vérifient que des scénarios d’utilisateurs finaux clés (comme la possibilité de se connecter au système ou d’échanger des messages instantanés) fonctionnent comme prévu. Pour Lync Server 2013, System Center Operations Manager peut exécuter les transactions synthétiques indiquées dans le tableau suivant. Trois types différents de transactions synthétiques sont répertoriés dans le tableau :

  - **Par défaut**. Il s’agit des transactions synthétiques qu’un nœud observateur exécute par défaut. Lorsque vous créez un nœud observateur, vous avez la possibilité de spécifier les transactions synthétiques qui seront exécutées par ce nœud. (C’est le but du paramètre Tests utilisé par l’applet de commande **New-CsWatcherNodeConfiguration**.) Si vous n’utilisez pas le paramètre Tests lorsque le nœud observateur est créé, il exécute automatiquement toutes les transactions synthétiques par défaut, mais n’exécute aucune des autres transactions synthétiques. Cela signifie, par exemple, que le nœud observateur est configuré pour exécuter le test Test-CsAddressBookService, mais qu’il n’est pas configuré pour exécuter le test Test-CsExumConnectivity.

  - **Non par défaut**. Comme leur nom l’indique, les transactions synthétiques non par défaut sont des tests qui ne sont pas exécutés par défaut par l’observateur. Cependant, le nœud observateur peut être autorisé à exécuter n’importe laquelle des transactions synthétiques non par défaut. Vous pouvez effectuer cette opération lorsque vous créez le nœud observateur (à l’aide de l’applet de commande **New-CsWatcherNodeConfiguration**) ou à tout moment par la suite. Bon nombre des transactions synthétiques non par défaut nécessitent des étapes de configuration supplémentaires. Pour plus d’informations, voir [Instructions d’installation spéciales pour les transactions synthétiques](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Étendu**. Les tests étendus sont un type spécial de transaction synthétique non par défaut. Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage. Cela peut s’avérer utile pour vérifier des comportements tels que plusieurs itinéraires des communications vocales PSTN pour un pool. Vous pouvez configurer ceci en ajoutant simplement plusieurs instances d’un test étendu à un nœud observateur.

Pour plus d’informations sur le processus d’ajout d’autres transactions synthétiques à un nœud observateur, voir [Gestion des nœuds observateurs](lync-server-2013-managing-watcher-nodes.md). Vous pouvez utiliser Lync Server Management Shell pour supprimer des transactions synthétiques d’un nœud observateur.

Parmi les transactions synthétiques accessibles aux nœuds observateur, citons les suivantes :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de l’applet de commande (nom du test)</th>
<th>Description</th>
<th>Type de transaction synthétique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts via HTTP.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Confirme que les utilisateurs peuvent envoyer des messages instantanés d’égal à égal.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Confirme que les utilisateurs peuvent passer des appels audio d’égal à égal (signalisation uniquement).</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>Confirme que les utilisateurs peuvent afficher la présence d’autres utilisateurs.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>Confirme que les utilisateurs peuvent se connecter à Lync.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Non utilisé pour la version sur site de Lync Server 2013.</p></td>
<td><p>Étendu</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros PSTN).</p></td>
<td><p>Non par défaut, étendu</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et participer à celles-ci.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirme que les serveurs Edge A/V peuvent accepter des connexions pour les appels et les téléconférences d’égal à égal.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données, une réunion en ligne qui comprend des activités telles que des tableaux blancs et des sondages.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Confirme qu’un utilisateur peut se connecter à la messagerie unifiée Exchange.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirme que les utilisateurs peuvent créer des réunions planifiées et y participer via un lien d’adresse web.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Confirme que les utilisateurs d’appareil mobile peuvent inscrire et envoyer des messages instantanés.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Confirme que les contacts d’un utilisateur sont accessibles via le magasin de contacts unifié. Le magasin de contacts unifié permet aux utilisateurs de tenir à jour un unique ensemble de contacts accessible via Lync 2013, Outlook et/ou Outlook Web Access.</p></td>
<td><p>Non par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirme qu’un message instantané peut être envoyé via la passerelle XMPP (Extensible Messaging and Presence Protocol).</p></td>
<td><p>Non par défaut</p></td>
</tr>
</tbody>
</table>


Il est inutile d’installer des nœuds observateur afin d’utiliser System Center Operations Manager. Si vous n’installez pas ces nœuds, vous pouvez toujours obtenir des alertes en temps réel des composants Lync Server 2013 lorsqu’un problème se produit. (Le pack Component and User Management n’utilise pas de nœuds observateur.) Toutefois, des nœuds observateur sont requis si vous souhaitez surveiller des scénarios de bout en bout à l’aide du pack Active Monitoring Management.

> [!NOTE]  
> Les administrateurs peuvent également exécuter des transactions synthétiques manuellement, et ce sans avoir besoin d’utiliser ou d’installer Operations Manager. Pour plus d’informations sur les applets de commande Test-Cs, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps">Index des applets de commande Lync Server 2013</a>.

En fonction de la taille de votre déploiement, les transactions synthétiques peuvent utiliser une grande quantité de mémoire d’ordinateur et de temps processeur. Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud observateur. Par exemple, il est déconseillé de configurer un serveur frontal comme nœud observateur. Les nœuds observateurs doivent répondre aux spécifications matérielles suivantes :

> [!NOTE]  
> Un nœud observateur Microsoft Lync Server 2010 hérité ne peut être colocalisé sur le même ordinateur avec un nœud observateur Lync Server 2013. Cela est dû au fait que les fichiers système principaux pour Lync Server 2010 et Lync Server 2013 ne peuvent pas se trouver sur le même ordinateur.<br />
Toutefois, les nœuds observateur Lync Server 2013 peuvent simultanément surveiller Lync Server 2013 et Lync Server 2010. Les transactions synthétiques par défaut sont prises en charge sur les deux versions du produit.

Les nœuds observateur Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur de l’entreprise pour vérifier les éléments suivants :

  -   
    Connectivité aux pools pour les utilisateurs au sein de l’entreprise

  -   
    Connectivité par le biais des réseaux de périmètre pour les utilisateurs distants qui travaillent à l’extérieur de l’entreprise

  -   
    Connectivité aux Branch Office Appliances

  -   
    Connectivité à Lync Server 2010 à l’intérieur de l’entreprise et par le biais des réseaux de périmètre

Différentes options d’authentification sont disponibles pour l’intérieur et l’extérieur de l’entreprise afin de simplifier l’administration. Pour plus d’informations, voir [Configuration d’un nœud observateur pour l’exécution des transactions synthétiques](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Pour configurer un ordinateur en tant que nœud observateur, vous devez effectuer les étapes suivantes après avoir installé System Center Operations Manager et importé les packs d’administration Lync Server 2013.

Avant d’installer les fichiers principaux Lync Server 2013 et les fichiers de l’agent System Center, vous devez également vous assurer que l’ordinateur du nœud observateur répond à toutes les conditions préalables à l’installation de Lync Server 2013. Par ailleurs, les éléments suivants doivent être installés sur l’ordinateur du nœud observateur :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Spécification minimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><p>L’un des éléments suivants :</p><ul><li><p>Processeur 64 bits, quadruple cœur 2,33 GHz ou supérieur</p></li><li><p>Processeur 64 bits à deux voies, double cœur, 2,33 GHz ou supérieur</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>8 Go</p></td>
</tr>
<tr class="odd">
<td><p>Système d’exploitation réseau</p></td>
<td><ul><li><p>1 carte réseau 1 Gbits/s</p></li><li><p>Windows Server 2008 R2, Windows Server 2012 ou</p>
<p>Windows Server 2012 R2</p></li></ul></td>
</tr>
</tbody>
</table>


  - Version complète du .NET Framework 4.5

  - Windows Identity Foundation

  - Windows PowerShell 3.0

Dès que toutes ces conditions préalables sont remplies, vous pouvez configurer le nœud observateur en effectuant les opérations suivantes :

  - Installation des fichiers principaux Lync Server 2013 sur l’ordinateur du nœud observateur

  - Installation de l’agent System Center Operations Manager sur l’ordinateur du nœud observateur

  - Exécution du fichier exécutable Watchernode.msi

  - Utilisation des applets de commande **CsWatcherNodeConfiguration** pour configurer les utilisateurs de test qui seront employés par le nœud observateur

