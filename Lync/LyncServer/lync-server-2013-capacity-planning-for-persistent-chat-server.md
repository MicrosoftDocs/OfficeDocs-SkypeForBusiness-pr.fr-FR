---
title: 'Lync Server 2013 : planification de la capacité pour le serveur de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Planification de la capacité pour le serveur de chat permanent dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Le serveur de chat permanent peut exécuter une discussion en temps réel avec plusieurs utilisateurs, qui peut être persistante lors de la récupération et de la recherche ultérieures. À la différence de la messagerie instantanée de groupe enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations est configuré, une session serveur de chat permanent reste ouverte plus longtemps et le contenu est enregistré sur un serveur, ainsi que les messages, les fichiers, les URL et les autres données faisant partie d’un conversation en cours.

La planification de la capacité est une partie importante de la préparation du déploiement d’un serveur de chat permanent. Cette rubrique fournit des détails sur les topologies du serveur de chat permanent prises en charge et les tables de planification de capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement. Il explique également comment gérer au mieux les déploiements de serveurs de chat permanent qui nécessitent une plus grande capacité aux heures de pointe.

Pour télécharger le serveur Chat permanent, voir « Microsoft Lync Server 13 persistent Chat Server [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)» à l’adresse.

Pour plus d’informations sur l’installation d’un serveur de chat permanent, voir [installer le serveur Chat permanent dans Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) et [configurer le serveur Chat permanent dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) dans la documentation de déploiement.

Les outils d’assistance, tels que l’outil de planification de Lync Server, peuvent vous aider à planifier la capacité. Pour plus d’informations sur l’outil de planification, voir [commencer le processus de planification de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologies prises en charge par le serveur Chat permanent

Vous pouvez déployer le serveur de chat permanent dans les pools serveur unique ou serveur multiples, avec une topologie à pool unique ou à plusieurs pools.

Nous prenons désormais en charge le serveur Chat permanent sur un serveur Standard Edition Server pour les nouveaux déploiements de Lync Server 2013. Toutefois, les performances et l’évolutivité seront affectées, et comme il n’existe aucune option de haute disponibilité pour ce nouveau déploiement, nous pensons que vous utiliserez principalement cette méthode dans le cadre de la preuve de concept, d’évaluation, etc.

<div>


> [!NOTE]  
> Pour plus d’informations sur les deux topologies, reportez-vous à la section <A href="lync-server-2013-planning-for-persistent-chat-server.md">planification du serveur de chat permanent dans Lync server 2013</A> dans cette documentation Set et <A href="lync-server-2013-deploying-persistent-chat-server.md">déploiement du serveur de conversation permanent dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="single-server-topology"></a>Topologie à serveur unique

La configuration minimum et le déploiement le plus simple pour le serveur de chat permanent est une topologie de serveur frontal de chat permanent unique. Ce déploiement nécessite un serveur unique exécutant chat permanent (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et si la conformité est requise, la base de données SQL Server pour stocker le données de conformité.

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de chat permanent démarré comme déploiement d’un serveur unique dans le générateur de topologie. Nous vous recommandons d’utiliser la topologie de pool multiserveur, même si vous utilisez un serveur unique. C’est pourquoi vous pourrez ajouter d’autres serveurs ultérieurement, si nécessaire. 


</div>

La figure suivante montre tous les composants obligatoires et facultatifs d’une topologie pour un seul serveur frontal de chat permanent avec conformité.

**Serveur de chat permanent unique**

![Topologie de serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie de serveur unique avec service de conformité")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie de plusieurs serveurs

Afin d’offrir une plus grande capacité et une fiabilité accrue, vous pouvez déployer une topologie multiserveur, comme décrit dans [planification pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologie multiserveur peut inclure jusqu’à quatre ordinateurs actifs exécutant chat permanent (les configurations de haute disponibilité et de récupération d’urgence peuvent prendre jusqu’à 8, mais seules quatre peuvent être actives et les quatre autres en veille). Chaque serveur peut prendre en charge autant d’utilisateurs simultanés qu' 20 000, soit un total d' 80 000 utilisateurs simultanés connectés à un pool de serveurs de chat permanent doté de 4 serveurs. Une topologie multiserveur est la même que celle de la topologie sur un serveur, à l’exception de l’hébergement de plusieurs serveurs et de la possibilité d’augmenter leur taille. Plusieurs ordinateurs exécutant un serveur Chat permanent doivent résider dans le même domaine de services de domaine Active Directory que Lync Server et le service de conformité.

La figure suivante montre tous les composants d’une topologie multiserveur avec plusieurs ordinateurs exécutant une conversation permanente serveur, le service de conformité facultatif et une base de données de conformité séparée.

**Plusieurs serveurs de chat permanent**

![Topologie de plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie de plusieurs serveurs")

Dans le cas d’un déploiement sur un serveur de chat permanent à quatre serveurs, où les utilisateurs de 80 000 peuvent se connecter à un serveur et utiliser une conversation permanente, le chargement est distribué de façon égale auprès des utilisateurs 20 000 par serveur. Si un serveur devient indisponible, les utilisateurs qui se connectent à ce serveur perdront leur accès au serveur Chat permanent. Ces utilisateurs déconnectés sont alors automatiquement transférés vers les serveurs restants jusqu’à ce que le serveur indisponible soit restauré. En fonction de la quantité de trafic de chat permanent sur le réseau, ce transfert peut prendre quelques minutes ou plus. Étant donné que chacun des serveurs restants peut héberger autant d’utilisateurs qu' 30 000, nous vous recommandons de restaurer le serveur non disponible aussi rapidement que possible pour éviter les problèmes de performances. Dans le cas contraire, vous pouvez rendre un autre serveur de chat permanent disponible via le générateur de topologie ou la cmdlet Windows PowerShell **Set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Planification de la capacité du serveur Chat permanent

Les tableaux suivants peuvent vous aider à planifier la capacité du serveur de chat permanent. Ils déterminent la manière dont les paramètres du serveur de conversation persistante affectent les capacités de capacité.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planification de votre capacité maximale pour le serveur de chat permanent

Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Exemple de capacité maximale du pool de serveurs chat chat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instances de service de chat permanent actives</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Instances de service de chat permanent</p></td>
<td><p><em>8 (4 doit être inactif ; seul un maximum de 4 peut être actif)</em></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs actifs connectés</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Nombre total d’utilisateurs approvisionnés</p></td>
<td><p>150,000</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de points de terminaison</p></td>
<td><p>120,000</p></td>
</tr>
</tbody>
</table>


Dans l’exemple ci-dessus, le plan doit prendre en charge le nombre maximal d’utilisateurs pouvant être conservés par un serveur de chat permanent : quatre serveurs/instances du service de chat permanent (peuvent comporter 4 serveurs plus passifs pour une disponibilité élevée et une reprise après sinistre) et 20 000 utilisateurs par serveur, pour un total de 80 000 utilisateurs actifs.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Planification de la capacité pour gérer l’accès aux salles de conversation permanente

L’exemple de tableau suivant peut vous aider à planifier la gestion de l’accès aux salles de conversation permanentes dans un pool de serveurs de chat permanent.

### <a name="managing-chat-room-access-sample"></a>Exemple de gestion de l’accès aux salles de conversation

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Salles de conversation de petite taille</th>
<th>Salles de conversation de taille moyenne</th>
<th>Salles de conversation de grande taille</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taille des salles de conversation (nombre d’utilisateurs connectés)</p></td>
<td><p>30 par salle</p></td>
<td><p>150 par salle</p></td>
<td><p>16 000 par salle</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles de conversation</p></td>
<td><p>32,000</p></td>
<td><p>1,067</p></td>
<td><p>0,10</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>% de salles auditorium</p></td>
<td><p>1 %</p></td>
<td><p>1 %</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% de salles ouvertes</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salles ouvertes (aucune appartenance explicite)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Salles non ouvertes (salles standard avec appartenance explicite)</p></td>
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5</p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>Salles auditorium (entrée de présentateurs supplémentaires)</p></td>
<td><p>0,4</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles gérées par appartenance directe</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salles gérées par groupes d’utilisateurs</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles ouvertes (non spécifiés explicitement)</p></td>
<td><p>0,4</p></td>
<td><p>0,4</p></td>
<td><p>0,4</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes</p></td>
<td><p>trente</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>0,10</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs et groupes d’utilisateurs dans la liste des gestionnaires de chaque salle de conversation (pour les salles ouvertes et non ouvertes)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utilisateurs et groupes d’utilisateurs dans la liste des présentateurs de chaque salle de conversation auditorium (pour les salles ouvertes et non ouvertes)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles non ouvertes</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entités basées sur les utilisateurs et groupes d’utilisateurs dans toutes les salles de conversation auditorium</p></td>
<td><p>0,4</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entités de gestionnaires basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de gestionnaires de salles de conversation</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs actifs par salle de conversation</p></td>
<td><p><em>trente</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles de conversation par utilisateur</p></td>
<td><p><em>midi</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>Seiz</em></p></td>
</tr>
<tr class="odd">
<td><p>Groupes d’utilisateurs dans chaque liste d’appartenance à une salle de conversation</p></td>
<td><p><em>0,10</em></p></td>
<td><p><em>0,10</em></p></td>
<td><p><em>0,15</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles gérées par groupes d’utilisateurs</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles de conversation</p></td>
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaires, de présentateurs et d’étendue de salles de conversation</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entrées de contrôle d’accès</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>Nombre maximum d’entrées de contrôle d’accès</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


Dans l’exemple ci-dessus, lorsque vous déployez les serveurs de chat permanent conformément aux recommandations recommandées, les utilisateurs peuvent gérer jusqu’à 80 000 utilisateurs actifs sur un pool de quatre serveurs avec conformité activée.

Cet exemple indique les catégories des salles de conversation : petite (30 utilisateurs actifs à tout moment), moyenne (150 utilisateurs actifs) et grande (16 000 utilisateurs actifs). Le nombre de salles de conversation d’une taille précise est calculé en fonction du nombre total de :

  - D’utilisateurs actifs dans le système

  - D’utilisateurs actifs dans les salles de conversation de la taille donnée

  - Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur

Pour chaque salle de conversation, le tableau de planification de capacité précédent spécifie le nombre d’entrées de contrôle d’accès associées à la salle de conversation, dont les entrées affectées directement à la salle de conversation. Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès. Vous pouvez également contrôler l’accès au niveau de la catégorie. Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être un groupe d’utilisateurs (par exemple, un groupe de sécurité, une liste de distribution ou un utilisateur unique). Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.

<div>


> [!IMPORTANT]  
> En planifiant votre stratégie de gestion des salles de conversation, gardez à l’esprit que le nombre total d’entrées de contrôle d’accès autorisées est de 2 millions. Si le nombre d’entrées de contrôle d’accès calculé dépasse 2 millions, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, quand cela s’avère possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs au lieu d’utilisateurs individuels.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Planification de la capacité pour gérer l’accès aux salles de conversation par invitation

Vous pouvez utiliser le tableau de planification des capacités suivant pour comprendre le nombre d’invitations créées et stockées par le serveur Chat permanent dans la base de données de chat permanent lorsque celui-ci est configuré pour envoyer des invitations. Pour gérer les invitations à une catégorie, vous devez utiliser la page **paramètres des catégories de salle de conversation** du panneau de configuration de Lync Server, ou à l’aide de l’applet de commande Windows PowerShell **Set-csPersistentChatCategory**. Vous pouvez gérer les invitations d’une salle de conversation (en fonction de ce que la catégorie autorise) à l’aide de la page de **gestion des salles** lancée par le client Lync, ou à l’aide d’une cmdlet Windows PowerShell, **Set-csPersistentChatRoom**.

Les exemples de données du tableau ci-après supposent que l’option **Invitations** est définie sur **Oui** dans la page **Paramètres de la salle de conversation** pour 50 % de toutes les salles de conversation.

<div>


> [!IMPORTANT]  
> Si la valeur calculée du nombre d’invitations générée par le serveur dépasse 1 million, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, assurez-vous de réduire le nombre de salles de conversation configurées pour envoyer des invitations ou limiter le nombre d’utilisateurs qui peuvent rejoindre des salles de conversation configurées pour envoyer des invitations.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Exemple d’accès à une salle de conversation par exemple d’invitation

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Salles de conversation de petite taille</th>
<th>Salles de conversation de taille moyenne</th>
<th>Salles de conversation de grande taille</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateurs pouvant accéder à la salle de conversation</p></td>
<td><p>30 par salle</p></td>
<td><p>150 par salle</p></td>
<td><p>16 000 par salle</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Pourcentage de salles qui ont des invitations</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salles de conversation configurées pour envoyer des invitations</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utilisateurs pouvant accéder à la salle de conversation</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Invitations générées par un serveur de chat permanent</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>Nombre maximal autorisé d’invitations</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
<tr class="odd">
<td><p>Modèle 1 - Démarrer avec le nombre attendu de messages par salle par jour</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Taux de conversation par salle (par jour)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation (par seconde) de toutes les salles</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modèle 2 - Démarrer avec le nombre de messages publiés par utilisateur par jour</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation par utilisateur par jour</p></td>
<td><p>0,15</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>CX3-20</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation par salle (par jour)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation (par seconde) de toutes les salles</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modèle d’utilisateur de performance serveur Chat permanent

Le tableau suivant décrit le modèle utilisateur pour le serveur de chat permanent. Il fournit les bases des conditions de planification de la capacité requises et représente une organisation type avec 80 000 utilisateurs simultanés sur quatre serveurs.

### <a name="persistent-chat-server-performance-user-model"></a>Modèle d’utilisateur de performance serveur Chat permanent

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Nombre d’utilisateurs actifs connectés</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’instances de service de chat permanent</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>Taille des petites salles de conversation</p></td>
<td><p>30 utilisateurs</p></td>
</tr>
<tr class="even">
<td><p>Taille des moyennes salles de conversation</p></td>
<td><p>150 utilisateurs</p></td>
</tr>
<tr class="odd">
<td><p>Taille des grandes salles de conversation</p></td>
<td><p>16 000 utilisateurs</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de salles de conversation</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de petites salles de conversation</p></td>
<td><p>32,000</p></td>
</tr>
<tr class="even">
<td><p>Nombre de moyennes salles de conversation</p></td>
<td><p>1,067</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de grandes salles de conversation</p></td>
<td><p>0,10</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de salles de conversation par utilisateur</p></td>
<td><p>Seiz</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de petites salles de conversation par utilisateur</p></td>
<td><p>midi</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de moyennes salles de conversation par utilisateur</p></td>
<td><p>deuxième</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de grandes salles de conversation par utilisateur</p></td>
<td><p>deuxième</p></td>
</tr>
<tr class="even">
<td><p>Nombre de salles jointes par utilisateur</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Taux maximal d’utilisateurs joints</p></td>
<td><p>10/seconde</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation total</p></td>
<td><p>24/seconde</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation pour les petites salles de conversation</p></td>
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation pour les moyennes salles de conversation</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation pour les grandes salles de conversation</p></td>
<td><p>~0.15/second</p></td>
</tr>
<tr class="even">
<td><p>Pourcentage des salles de conversation configurées pour les invitations</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Pourcentage des appartenances directes</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Pourcentage des appartenances aux groupes</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Nombre moyen d’affiliations d’ancêtre dans les services de domaine Active Directory</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Nombre de contacts abonnés par utilisateur</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Nombre moyen de points de terminaison par utilisateur</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>Nombre moyen de salles de conversation visibles par point de terminaison</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>Nombre moyen de salles de conversation visibles par utilisateur</p></td>
<td><p>2,25 (50 % pour une salle et 50 % pour 2 salles) ; jusqu’à 6 salles ouvertes, une par moniteur</p></td>
</tr>
<tr class="even">
<td><p>Nombre de participants interrogés par intervalle</p></td>
<td><p>25 par salle de conversation visible</p></td>
</tr>
<tr class="odd">
<td><p>Durée de la fréquence d’interrogation</p></td>
<td><p>5 minutes</p></td>
</tr>
<tr class="even">
<td><p>Nombre de participants interrogés par seconde</p></td>
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de changements du statut de présence par heure et par utilisateur</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Nombre de changements du statut de présence par seconde</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

