---
title: "Lync Server 2013 : Plan. de capacité pr le serveur de conv. permanente"
TOCTitle: Planification de capacité pour le serveur de conversation permanente
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615006(v=OCS.15)
ms:contentKeyID: 49297814
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de capacité pour le serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le serveur de conversations permanentes permet d’engager une conversation à plusieurs en temps réel, pouvant perdurer pour des futures récupérations et recherches. À la différence de la messagerie instantanée de groupe, laquelle est enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations est configuré, une session du serveur de conversations permanentes reste ouverte plus longtemps et le contenu est enregistré sur un serveur, avec les messages, fichiers, URL et autres données faisant partie d’une conversation suivie.

La planification de capacité est une partie importante de la préparation du déploiement du serveur de conversations permanentes. Cette rubrique donne des informations sur les topologies de serveur de conversations permanentes prises en charge et les tables de planning de capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement. Elle décrit également comment gérer au mieux les déploiements de serveur de conversations permanentes nécessitant une plus grande capacité aux heures de pointe.

Pour télécharger serveur de conversations permanentes, reportez-vous à « Microsoft Lync Server 13 serveur de conversations permanentes» à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).

Pour plus d’informations sur l’installation du serveur de conversations permanentes, reportez-vous à [Installation du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) et [Configuration du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) dans la documentation de déploiement.

Des outils de support, comme l’outil de planification de Lync Server, peuvent vous aider davantage dans la planification de la capacité. Pour plus d’informations sur l’outil de planification, reportez-vous à [Début du processus de planification pour Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.

## Topologies prises en charge du serveur de conversations permanentes

Vous pouvez déployer le serveur de conversations permanentes dans une topologie à serveur unique ou à plusieurs serveurs et avec une topologie à pool unique ou à plusieurs pools.

Désormais, nous prenons également en charge le serveur de conversations permanentes sur le serveur Standard Edition pour les nouveaux déploiements de Lync Server 2013. Cependant, les performances et l’extensibilité sont affectées, et puisqu’il n’existe pas d’option de haute disponibilité pour ce nouveau déploiement, vous êtes priés de l’utiliser principalement à des fins de preuve de concept, d’évaluation, etc.

> [!NOTE]  
> Pour plus d’informations sur ces deux topologies, reportez-vous à <a href="lync-server-2013-planning-for-persistent-chat-server.md">Planification du serveur de conversation permanente dans Lync Server 2013</a> dans cette documentation et <a href="lync-server-2013-deploying-persistent-chat-server.md">Déploiement d’un serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement.

## Topologie à serveur unique

La configuration minimale et le déploiement le plus simple pour le serveur de conversations permanentes est une topologie avec un serveur frontal de serveur de conversations permanentes unique. Ce déploiement requiert un serveur unique qui exécute le serveur de conversations permanentes (qui exécute éventuellement le service de conformité si la conformité est activée), un serveur qui héberge la base de données SQL Server et, si la conformité est obligatoire, la base de données SQL Server pour stocker les données de conformité.

> [!IMPORTANT]  
> Vous ne pouvez pas ajouter d’autres serveurs à un pool de serveurs de conversations permanentes que vous avez commencé en tant que déploiement à serveur unique dans le Générateur de topologie. Nous vous recommandons d’utiliser la topologie à plusieurs pools de serveurs, même si vous utilisez un seul serveur afin de pouvoir ajouter d’autres serveurs ultérieurement, si besoin.

La figure suivante présente tous les composants obligatoires et facultatifs d’une topologie pour un seul serveur frontalserveur de conversations permanentes avec conformité.

**Serveur de conversations permanentes unique**

![Topologie à un serveur avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie à un serveur avec service de conformité")

## Topologie à plusieurs serveurs

Pour offrir une capacité et une fiabilité supérieures, vous pouvez déployer une topologie à plusieurs serveurs, comme indiqué dans [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant le serveur de conversations permanentes (les configurations à haute disponibilité et de récupération d’urgence autorisent jusqu’à huit ordinateurs, mais seuls quatre peuvent être actifs, les quatre autres étant en attente). Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, pour un total de 80 000 utilisateurs connectés simultanément à un pool de serveurs de conversations permanentes avec 4 serveurs. Une topologie à plusieurs serveurs est identique à une topologie à serveur unique, à la différence près que plusieurs serveurs hébergent le serveur de conversations permanentes et qu’elle offre une extensibilité supérieure. Plusieurs ordinateurs exécutant le serveur de conversations permanentes doivent se trouver dans le même domaine des services de domaine Active Directory que Lync Server et le service de conformité.

L’illustration suivante montre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant un serveur de conversations permanentes, le service de conformité facultatif et une base de données de conformité distincte.

**Plusieurs serveurs de conversation permanente**

![Topologie à plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie à plusieurs serveurs")

Dans un déploiement du serveur de conversations permanentes sur quatre serveurs, dans lequel 80 000 utilisateurs peuvent se connecter simultanément et utiliser la conversation permanente, la charge est distribuée uniformément en 20 000 utilisateurs par serveur. Si un serveur devient indisponible, les utilisateurs qui y sont connectés perdent leur accès au serveur de conversations permanentes. Les utilisateurs déconnectés sont automatiquement transférés sur les serveurs restants jusqu’au rétablissement du serveur indisponible. En fonction de la taille du trafic de conversation permanente sur le réseau, ce transfert peut prendre de quelques minutes ou plus. Du fait que les serveurs restants risquent d’héberger jusqu’à 30 000 utilisateurs, nous vous conseillons de rétablir le serveur indisponible le plus vite possible pour éviter des problèmes de performance. Sinon, vous pouvez rendre un autre serveur de conversations permanentes disponible à l’aide du Générateur de topologie ou de l’applet de commande Windows PowerShell**set-CsPersistentChatActiveServer**.

## Planification de la capacité du serveur de conversations permanentes

Les tableaux suivants vous permettent de faciliter la planification de la capacité du serveur de conversations permanentes. Ils modélisent l’impact sur les fonctionnalités de capacité selon la manière dont les différents paramètres du serveur de conversations permanentes sont modifiés.

## Planification de votre capacité maximale pour le serveur de conversations permanentes

Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.

### Exemple de capacité maximale du pool de serveurs de conversations permanentes

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instances du service de conversation permanente actives</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Instances du service de conversation permanente</p></td>
<td><p><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs actifs connectés</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Nombre total d’utilisateurs approvisionnés</p></td>
<td><p>150 000</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de points de terminaison</p></td>
<td><p>120 000</p></td>
</tr>
</tbody>
</table>


Dans l’exemple précédent, l’idée est de prendre en charge le nombre maximal d’utilisateurs autorisé par le serveur de conversations permanentes : quatre serveurs/instances du service de conversation permanente (avec éventuellement quatre serveurs passifs supplémentaires exécutant le serveur de conversations permanentes pour la haute disponibilité et la récupération d’urgence) et 20 000 utilisateurs par serveur, soit un total de 80 000 utilisateurs actifs.

## Planification de la capacité pour la gestion de l’accès à la salle de conversation permanente

L’exemple de tableau suivant vous permet de planifier la gestion de l’accès à la salle de conversation permanente dans un pool de serveurs de conversations permanentes.

### Exemple de gestion de l’accès à la salle de conversation

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
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salles de conversation</p></td>
<td><p>32 000</p></td>
<td><p>1 067</p></td>
<td><p>10</p></td>
<td><p>33 077</p></td>
</tr>
<tr class="odd">
<td><p>% de salles auditorium</p></td>
<td><p>1 %</p></td>
<td><p>1 %</p></td>
<td><p>50 %</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>% de salles ouvertes</p></td>
<td><p>3 %</p></td>
<td><p>3 %</p></td>
<td><p>50 %</p></td>
<td><p></p></td>
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
<td><p>31 040</p></td>
<td><p>1,035</p></td>
<td><p>5</p></td>
<td><p>32 080</p></td>
</tr>
<tr class="odd">
<td><p>Salles auditorium (entrée de présentateurs supplémentaires)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salles gérées par appartenance directe</p></td>
<td><p>50 %</p></td>
<td><p>10 %</p></td>
<td><p>0 %</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Salles gérées par groupes d’utilisateurs</p></td>
<td><p>50 %</p></td>
<td><p>90 %</p></td>
<td><p>100 %</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles ouvertes (non spécifiés explicitement)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16 000</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs et groupes d’utilisateurs dans la liste des gestionnaires de chaque salle de conversation (pour les salles ouvertes et non ouvertes)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs et groupes d’utilisateurs dans la liste des présentateurs de chaque salle de conversation auditorium (pour les salles ouvertes et non ouvertes)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes</p></td>
<td><p>465 600</p></td>
<td><p>15 520</p></td>
<td><p>-</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles non ouvertes</p></td>
<td><p>46 560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entités basées sur les utilisateurs et groupes d’utilisateurs dans toutes les salles de conversation auditorium</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Entités de gestionnaires basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de gestionnaires de salles de conversation</p></td>
<td><p>192 000</p></td>
<td><p>6 400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs actifs par salle de conversation</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salles de conversation par utilisateur</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Groupes d’utilisateurs dans chaque liste d’appartenance à une salle de conversation</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salles gérées par groupes d’utilisateurs</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles de conversation</p></td>
<td><p>155 200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation</p></td>
<td><p>465 600</p></td>
<td><p>77 600</p></td>
<td><p>72 000</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaires, de présentateurs et d’étendue de salles de conversation</p></td>
<td><p>192 000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entrées de contrôle d’accès</p></td>
<td><p>704 160</p></td>
<td><p>26 768</p></td>
<td><p>160</p></td>
<td><p>731 088</p></td>
</tr>
<tr class="even">
<td><p>Nombre maximum d’entrées de contrôle d’accès</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2 000 000</p></td>
</tr>
</tbody>
</table>


Dans l’exemple précédent, lorsque vous déployez les serveurs de conversations permanentes conformément aux instructions préconisées, ils peuvent gérer jusqu’à 80 000 utilisateurs actifs sur un pool de quatre serveurs avec la conformité activée.

Cet exemple indique les catégories des salles de conversation : petite (30 utilisateurs actifs à tout moment), moyenne (150 utilisateurs actifs) et grande (16 000 utilisateurs actifs). Le nombre de salles de conversation d’une certaine taille est calculé en fonction du nombre total :

  - D’utilisateurs actifs dans le système

  - D’utilisateurs actifs dans les salles de conversation de la taille donnée

  - Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur

Pour chaque salle de conversation, le tableau de planification de capacité précédent spécifie le nombre d’entrées de contrôle d’accès associées à la salle de conversation, dont les entrées affectées directement à la salle de conversation. Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès. Vous pouvez également contrôler l’accès au niveau de la catégorie. Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être un groupe d’utilisateurs (par exemple, un groupe de sécurité, une liste de distribution ou un utilisateur unique). Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.

> [!IMPORTANT]  
> En planifiant votre stratégie de gestion des salles de conversation, gardez à l’esprit que le nombre total d’entrées de contrôle d’accès autorisées est de 2 millions. Si le nombre d’entrées de contrôle d’accès calculé dépasse 2 millions, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, quand cela s’avère possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs au lieu d’utilisateurs individuels.

## Planification de capacité pour la gestion de l’accès à la salle de conversation par invitation

Vous pouvez utiliser la table de planification de la capacité suivante pour comprendre le nombre d’invitations que le serveur de conversations permanentes crée et stocke dans la base de données de conversation permanente lorsqu’elle est configurée pour envoyer des invitations. Vous gérez les invitations depuis Catégorie à l’aide de la page **Paramètres de catégorie de salle de conversation** dans le Panneau de configuration Lync Server, ou à l’aide de l’applet de commande Windows PowerShell, **set-csPersistentChatCategory**. Vous pouvez gérer des invitations dans une salle de conversation (conformément à ce qu’autorise la catégorie) à l’aide de la page **Gestion de salles** lancée depuis le client Lync ou à l’aide de l’applet de commande Windows PowerShell, **set-csPersistentChatRoom**.

Les exemples de données du tableau ci-après supposent que l’option **Invitations** est définie sur **Oui** dans la page **Paramètres de la salle de conversation** pour 50 % de toutes les salles de conversation.

> [!IMPORTANT]  
> Si la valeur calculée du nombre d’invitations générée par le serveur dépasse 1 million, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, assurez-vous de réduire au minimum le nombre de salles de conversation configurées pour envoyer des invitations, ou limitez le nombre d’utilisateurs pouvant se joindre aux salles de conversation ayant été configurées pour envoyer des invitations.

### Exemple d’accès à la salle de conversation par invitation

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
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Pourcentage de salles qui ont des invitations</p></td>
<td><p>50 %</p></td>
<td><p>50 %</p></td>
<td><p>50 %</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Salles de conversation configurées pour envoyer des invitations</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs pouvant accéder à la salle de conversation</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Invitations générées par le serveur de conversations permanentes</p></td>
<td><p>960 000</p></td>
<td><p>120 000</p></td>
<td><p>80 000</p></td>
<td><p>1 160 000</p></td>
</tr>
<tr class="even">
<td><p>Nombre maximal autorisé d’invitations</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2 000 000</p></td>
</tr>
<tr class="odd">
<td><p>Modèle 1 - Démarrer avec le nombre attendu de messages par salle par jour</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modèle 2 - Démarrer avec le nombre de messages publiés par utilisateur par jour</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation par utilisateur par jour</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
<td><p>0,1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation par salle (par jour)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1 213</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation (par seconde) de toutes les salles</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


## Modèle utilisateur des performances du serveur de conversations permanentes

Le tableau ci-dessous décrit le modèle utilisateur pour le serveur de conversations permanentes. Il fournit les bases des conditions de planification de la capacité requises et représente une organisation type avec 80 000 utilisateurs simultanés sur quatre serveurs.

### Modèle utilisateur des performances du serveur de conversations permanentes

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Nombre d’utilisateurs actifs connectés</p></td>
<td><p>80 000</p></td>
</tr>
<tr class="even">
<td><p>Nombre d’instances du service du serveur de conversations permanentes</p></td>
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
<td><p>33 077</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de petites salles de conversation</p></td>
<td><p>32 000</p></td>
</tr>
<tr class="even">
<td><p>Nombre de moyennes salles de conversation</p></td>
<td><p>1 067</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de grandes salles de conversation</p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de salles de conversation par utilisateur</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de petites salles de conversation par utilisateur</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de moyennes salles de conversation par utilisateur</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Nombre total de grandes salles de conversation par utilisateur</p></td>
<td><p>2</p></td>
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
<td><p>22,22/seconde</p></td>
</tr>
<tr class="even">
<td><p>Taux de conversation pour les moyennes salles de conversation</p></td>
<td><p>1,67/seconde</p></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation pour les grandes salles de conversation</p></td>
<td><p>~0,15/seconde</p></td>
</tr>
<tr class="even">
<td><p>Pourcentage des salles de conversation configurées pour les invitations</p></td>
<td><p>50 %</p></td>
</tr>
<tr class="odd">
<td><p>Pourcentage des appartenances directes</p></td>
<td><p>50 %</p></td>
</tr>
<tr class="even">
<td><p>Pourcentage des appartenances aux groupes</p></td>
<td><p>50 %</p></td>
</tr>
<tr class="odd">
<td><p>Nombre moyen d’affiliations anciennes dans services de domaine Active Directory</p></td>
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
<td><p>15 000</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de changements du statut de présence par heure et par utilisateur</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Nombre de changements du statut de présence par seconde</p></td>
<td><p>133,33</p></td>
</tr>
</tbody>
</table>

