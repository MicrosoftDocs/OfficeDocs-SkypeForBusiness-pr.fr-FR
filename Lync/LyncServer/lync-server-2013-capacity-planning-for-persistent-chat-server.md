---
title: 'Lync Server 2013 : planification de la capacité pour le serveur de conversation permanente'
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
ms.openlocfilehash: 5c6bb3c7dcd8d03ffb0a57fb165fe1dba4ee933d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512801"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Planification de la capacité pour le serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Le serveur de conversation permanente peut effectuer une conversation en temps réel multi-utilisateur pouvant être conservée pour la récupération et la recherche futures. Contrairement à la messagerie instantanée de groupe enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations est configuré, une session de serveur de conversation permanente reste ouverte plus longtemps et le contenu est enregistré sur un serveur, ainsi que les messages, les fichiers, les URL et d’autres données qui font partie d’une conversation en cours.

La planification de la capacité est un élément important de la préparation du déploiement du serveur de conversation permanente. Cette rubrique fournit des informations sur les topologies de serveur de conversation permanente prises en charge et les tables de planification de la capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement. Il décrit également comment gérer au mieux les déploiements de serveurs de conversation permanente qui nécessitent une plus grande capacité aux heures de pointe.

Pour télécharger le serveur de conversation permanente, voir « Microsoft Lync Server 13 persistent Chat Server » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) .

Pour plus d’informations sur l’installation du serveur de conversation permanente, voir [Installing persistent Chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) et [Configuring persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) dans la documentation de déploiement.

Les outils de support, tels que l’outil de planification Lync Server, peuvent vous aider à planifier la capacité. Pour plus d’informations sur l’outil de planification, voir [démarrage du processus de planification pour Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologies prises en charge par le serveur de conversation permanente

Vous pouvez déployer un serveur de conversation permanente dans des pools à serveur unique ou à plusieurs serveurs, ainsi qu’avec une topologie à pool unique ou à pool multiple.

Nous pouvons également prendre en charge le serveur de conversation permanente sur le serveur Standard Edition pour les nouveaux déploiements Lync Server 2013. Toutefois, les performances et l’évolutivité seront affectées, et étant donné qu’il n’existe aucune option de haute disponibilité pour ce nouveau déploiement, nous pensons que vous l’utiliserez principalement à des fins de preuve de concept, d’évaluation, et ainsi de suite.

<div>


> [!NOTE]  
> Pour plus d’informations sur les deux topologies, voir <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent Chat Server in Lync server 2013</A> dans cette documentation Set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent Chat Server in Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="single-server-topology"></a>Topologie à serveur unique

La configuration minimale et le déploiement le plus simple pour le serveur de conversation permanente est une seule topologie de serveur frontal de serveur de conversation permanente. Ce déploiement nécessite un serveur unique qui exécute le serveur de conversation permanente (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et, si la conformité est requise, la base de données SQL Server pour stocker les données de conformité.

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas ajouter d’autres serveurs à un pool de serveurs de conversation permanente qui est démarré en tant que déploiement à serveur unique dans le générateur de topologie. Nous vous recommandons d’utiliser la topologie de pools à plusieurs serveurs, même si vous utilisez un serveur unique. Cela vous permettra de pouvoir ajouter d’autres serveurs ultérieurement, si nécessaire. 


</div>

La figure suivante illustre tous les composants requis et facultatifs d’une topologie pour un seul serveur frontal de serveur de conversation permanente avec conformité.

**Serveur de conversations permanentes unique**

![Topologie à serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie à serveur unique avec service de conformité")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie à plusieurs serveurs

Pour augmenter la capacité et la fiabilité, vous pouvez déployer une topologie à plusieurs serveurs, comme décrit dans la rubrique [Planning for persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant un serveur de conversation permanente (les configurations de haute disponibilité et de récupération d’urgence autorisent jusqu’à huit, mais seulement quatre peuvent être actives et les quatre autres en attente). Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, soit un total de 80 000 utilisateurs simultanés connectés à un pool de serveurs de conversation permanente avec 4 serveurs. Une topologie à plusieurs serveurs est identique à la topologie à serveur unique, à ceci près que plusieurs serveurs hébergent le serveur de conversation permanente et peuvent être plus évolutifs. Plusieurs ordinateurs exécutant le serveur de conversation permanente doivent résider dans le même domaine des services de domaine Active Directory que Lync Server et le service de conformité.

La figure suivante illustre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant un serveur de conversation permanente, le service de conformité facultatif et une base de données de conformité distincte.

**Plusieurs serveurs de conversation permanente**

![Topologie à plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie à plusieurs serveurs")

Dans un déploiement de serveur de conversation permanente à quatre serveurs, où 80 000 utilisateurs peuvent être simultanément connectés à et utilisant la conversation permanente, la charge est distribuée uniformément à 20 000 utilisateurs par serveur. Si un serveur devient indisponible, les utilisateurs qui sont connectés à ce serveur perdront leur accès au serveur de conversation permanente. Les utilisateurs déconnectés seront automatiquement transférés sur les serveurs restants jusqu’au rétablissement du serveur indisponible. En fonction de la quantité de trafic de conversation permanente sur le réseau, ce transfert peut prendre quelques minutes ou plus. Étant donné que chacun des autres serveurs peut héberger jusqu’à 30 000 utilisateurs, nous vous recommandons de restaurer le serveur indisponible aussi rapidement que possible afin d’éviter les problèmes de performances. Dans le cas contraire, vous pouvez créer un autre serveur de conversation permanente à l’aide du générateur de topologies ou de l’applet de commande Windows PowerShell, **Set-applet cspersistentchatactiveserver**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Planification de la capacité du serveur de conversation permanente

Les tableaux suivants peuvent vous aider à planifier la capacité du serveur de conversation permanente. Ils modélisent comment la modification de différents paramètres du serveur de conversation permanente affecte les capacités de capacité.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planification de la capacité maximale pour le serveur de conversation permanente

Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Exemple de capacité maximale du pool de serveurs de conversation permanente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instances actives du service de conversation permanente</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Instances du service de conversation permanente</p></td>
<td><p><em>8 (4 doit être inactif ; seul un maximum de 4 peut être actif)</em></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs actifs connectés</p></td>
<td><p><em>80 000</em></p></td>
</tr>
<tr class="even">
<td><p>Nombre total d’utilisateurs approvisionnés</p></td>
<td><p>150 000</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de points de terminaison</p></td>
<td><p>120 000</p></td>
</tr>
</tbody>
</table>


Dans l’exemple précédent, le plan doit prendre en charge le nombre maximal d’utilisateurs autorisé par le serveur de conversation permanente : quatre serveurs/instances du service de conversation permanente (il peut avoir quatre serveurs passifs plus passifs exécutant le serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence) et 20 000 utilisateurs par serveur, pour un total de 80 000 utilisateurs actifs.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Planification de la capacité pour la gestion de l’accès aux salles de conversation permanente

L’exemple de tableau suivant peut vous aider à planifier la gestion de l’accès aux salles de conversation permanente dans un pool de serveurs de conversation permanente.

### <a name="managing-chat-room-access-sample"></a>Exemple de gestion de l’accès à la salle de conversation

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
<th>Petites salles de conversation</th>
<th>Salles de conversation moyennes</th>
<th>Grandes salles de conversation</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taille des salles de conversation (nombre d’utilisateurs connectés)</p></td>
<td><p>30 par salle</p></td>
<td><p>150 par salle</p></td>
<td><p>16 000 par salle</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles de conversation</p></td>
<td><p>32 000</p></td>
<td><p>1 067</p></td>
<td><p>10 </p></td>
<td><p>33 077</p></td>
</tr>
<tr class="odd">
<td><p>% de salles Auditorium</p></td>
<td><p>1 %</p></td>
<td><p>1 %</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% de salles ouvertes</p></td>
<td><p>3 %</p></td>
<td><p>3 %</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salles ouvertes (pas d’appartenance explicite)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Salles non ouvertes (salles standard avec appartenance explicite)</p></td>
<td><p>31 040</p></td>
<td><p>1,035</p></td>
<td><p>5 </p></td>
<td><p>32 080</p></td>
</tr>
<tr class="odd">
<td><p>Salles Auditorium (entrée autres présentateurs supplémentaires)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles gérées par l’appartenance directe</p></td>
<td><p>50%</p></td>
<td><p>10 %</p></td>
<td><p>0 %</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salles gérées par groupes d’utilisateurs</p></td>
<td><p>50%</p></td>
<td><p>90 %</p></td>
<td><p>100 %</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Groupes d’utilisateurs dans la liste d’appartenance de chaque salle de conversation pour les salles ouvertes (non spécifié explicitement)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs de la liste d’appartenance de chaque salle de conversation pour les salles non ouvertes</p></td>
<td><p>0,30</p></td>
<td><p>150</p></td>
<td><p>16 000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Groupes d’utilisateurs dans la liste d’appartenance de chaque salle de conversation pour les salles non ouvertes</p></td>
<td><p>3</p></td>
<td><p>5 </p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires de la salle de conversation (pour les salles ouvertes et non ouvertes)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utilisateurs et groupes d’utilisateurs dans la liste présentateurs de la salle de conversation de type Auditorium (pour les salles ouvertes et non ouvertes)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes</p></td>
<td><p>465 600</p></td>
<td><p>15 520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles non ouvertes</p></td>
<td><p>46 560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entités basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les salles de conversation de type Auditorium</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entités de gestionnaire basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de gestionnaires de salles de conversation</p></td>
<td><p>192 000</p></td>
<td><p>6 400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs actifs par salle de conversation</p></td>
<td><p><em>0,30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16 000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salles de conversation par utilisateur</p></td>
<td><p><em>an</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>Seiz</em></p></td>
</tr>
<tr class="odd">
<td><p>Groupes d’utilisateurs dans chaque liste d’appartenance à une salle de conversation</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
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
<td><p>155 200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation</p></td>
<td><p>465 600</p></td>
<td><p>77 600</p></td>
<td><p>72 000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaires, de présentateurs et d’étendue de salles de conversation</p></td>
<td><p>192 000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entrées de contrôle d’accès</p></td>
<td><p>704 160</p></td>
<td><p>26 768</p></td>
<td><p>160</p></td>
<td><p>731 088</p></td>
</tr>
<tr class="even">
<td><p>Nombre maximum d’entrées de contrôle d’accès</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 millions</p></td>
</tr>
</tbody>
</table>


Dans l’exemple précédent, lorsque vous déployez les serveurs de conversation permanente conformément aux instructions recommandées, ils peuvent gérer jusqu’à 80 000 utilisateurs actifs sur un pool de quatre serveurs avec la conformité activée.

Cet exemple montre les salles de conversation classées comme petites (30 utilisateurs actifs à tout moment), moyennes (150 utilisateurs actifs) et grande (16 000 utilisateurs actifs). Le nombre de salles de conversation d’une certaine taille est calculé en fonction du nombre total :

  - D’utilisateurs actifs dans le système

  - D’utilisateurs actifs dans les salles de conversation de la taille donnée

  - Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur

Pour chaque salle de conversation, la table de planification de la capacité précédente spécifie le nombre d’entrées de contrôle d’accès qui sont associées à la salle de conversation, y compris les entrées affectées directement à la salle de conversation. Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès. Vous pouvez également contrôler l’accès au niveau de la catégorie. Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être un groupe d’utilisateurs (par exemple, un groupe de sécurité, une liste de distribution ou un utilisateur unique). Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.

<div>


> [!IMPORTANT]  
> Lors de la planification de votre stratégie de gestion des salles de conversation, gardez à l’esprit que le nombre total d’entrées de contrôle d’accès autorisé est de 2 millions. Si les entrées de contrôle d’accès calculé dépassent 2 millions, les performances du serveur peuvent se dégrader de manière significative. Pour éviter ce problème, dans la mesure du possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs au lieu d’utilisateurs individuels.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Planification de capacité pour la gestion de l’accès à la salle de conversation par invitation

Vous pouvez utiliser le tableau de planification de la capacité suivant pour comprendre le nombre d’invitations que le serveur de conversation permanente crée et stocke dans la base de données de conversation permanente lorsqu’il est configuré pour envoyer des invitations. Vous gérez les invitations de la catégorie à l’aide de la page **paramètres de catégorie de salle de conversation** dans le panneau de configuration Lync Server, ou à l’aide de l’applet de commande Windows PowerShell, **Set-applet cspersistentchatcategory**. Vous pouvez gérer les invitations d’une salle de conversation (en fonction de ce que la catégorie autorise) à l’aide de la page de **gestion des salles** lancée à partir du client Lync, ou à l’aide d’une applet de commande Windows PowerShell, **Set-applet cspersistentchatroom**.

Les exemples de données du tableau suivant supposent que, sur la page des paramètres de la **salle de conversation** de 50% de toutes les salles de conversation, l’option **invitations** est définie sur **Oui**.

<div>


> [!IMPORTANT]  
> Si la valeur calculée pour le nombre d’invitations générée par le serveur dépasse 1 million, les performances du serveur peuvent se dégrader de manière significative. Pour éviter ce problème, veillez à réduire le nombre de salles de conversation configurées pour envoyer des invitations ou à limiter le nombre d’utilisateurs pouvant rejoindre des salles de conversation configurées pour envoyer des invitations.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Exemple d’accès à la salle de conversation par invitation

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
<th>Petites salles de conversation</th>
<th>Salles de conversation moyennes</th>
<th>Grandes salles de conversation</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateurs pouvant accéder à la salle de conversation</p></td>
<td><p>30 par salle</p></td>
<td><p>150 par salle</p></td>
<td><p>16 000 par salle</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Pourcentage de salles ayant des invitations</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salles de conversation configurées pour envoyer des invitations</p></td>
<td><p><em>16 000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>disque</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utilisateurs pouvant accéder à la salle de conversation</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16 000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Invitations générées par le serveur de conversation permanente</p></td>
<td><p>960 000</p></td>
<td><p>120 000</p></td>
<td><p>80 000</p></td>
<td><p>1 160 000</p></td>
</tr>
<tr class="even">
<td><p>Nombre maximal autorisé d’invitations</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 millions</p></td>
</tr>
<tr class="odd">
<td><p>Modèle 1-démarrer avec le nombre prévu de messages par salle et par jour</p></td>
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
<td><p>Taux de conversation (par seconde) dans toutes les salles</p></td>
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modèle 2-Démarrer avec le nombre de messages publiés par utilisateur et par jour</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation par utilisateur et par jour</p></td>
<td><p>15 </p></td>
<td><p>5 </p></td>
<td><p>0,1</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation par salle (par jour)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1 213</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation (par seconde) dans toutes les salles</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modèle utilisateur des performances du serveur de conversation permanente

Le tableau suivant décrit le modèle utilisateur pour le serveur de conversation permanente. Elle fournit la base des exigences de planification de la capacité et représente une organisation classique avec 80 000 utilisateurs simultanés sur quatre serveurs.

### <a name="persistent-chat-server-performance-user-model"></a>Modèle utilisateur des performances du serveur de conversation permanente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Nombre d’utilisateurs actifs connectés</p></td>
<td><p>80 000</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’instances de service du serveur de conversation permanente</p></td>
<td><p>4 </p></td>
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
<td><p>16 000 utilisateurs</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de salles de conversation</p></td>
<td><p>33 077</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de petites salles de conversation</p></td>
<td><p>32 000</p></td>
</tr>
<tr class="even">
<td><p>Nombre de moyennes salles de conversation</p></td>
<td><p>1 067</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de grandes salles de conversation</p></td>
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>Nombre total de salles de conversation par utilisateur</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de petites salles de conversation par utilisateur</p></td>
<td><p>12 </p></td>
</tr>
<tr class="even">
<td><p>Nombre total de moyennes salles de conversation par utilisateur</p></td>
<td><p>n°2</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de grandes salles de conversation par utilisateur</p></td>
<td><p>n°2</p></td>
</tr>
<tr class="even">
<td><p>Nombre de salles jointes par utilisateur</p></td>
<td><p>heures/24</p></td>
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
<td><p>22.22/seconde</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation pour les moyennes salles de conversation</p></td>
<td><p>1.67/seconde</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation pour les grandes salles de conversation</p></td>
<td><p>~ 0,15/seconde</p></td>
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
<td><p>Nombre moyen d’affiliations ancêtres dans les services de domaine Active Directory</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Nombre de contacts abonnés par utilisateur</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Nombre moyen de points de terminaison par utilisateur</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Nombre moyen de salles de conversation visibles par point de terminaison</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Nombre moyen de salles de conversation visibles par utilisateur</p></td>
<td><p>2,25 (50% pour une salle de 1 et 50% pour 2 salles); Jusqu’à 6 salles ouvertes, une par moniteur</p></td>
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
<td><p>15 000</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de changements du statut de présence par heure et par utilisateur</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>Nombre de changements du statut de présence par seconde</p></td>
<td><p>133,33</p></td>
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

