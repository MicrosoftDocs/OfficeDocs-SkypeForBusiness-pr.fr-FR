---
title: "Lync Server 2013 : Conf. requise pour la résistance des sites de succursale"
TOCTitle: Configuration requise pour la résistance des sites de succursale
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412772(v=OCS.15)
ms:contentKeyID: 49298411
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour la résistance des sites de succursale pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.

## Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparez les utilisateurs à la résistance des sites de succursale en définissant leur pool de serveurs d’inscriptions comme le Survivable Branch Appliance (SBA) ou le serveur Survivable Branch Server.

## Affectations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résistance de site de succursale choisie, vous devez affecter un serveur d’inscriptions principal à chaque utilisateur. Les utilisateurs de sites de succursale doivent toujours s’inscrire auprès du serveur d’inscriptions du site de succursale, indépendamment du fait que le serveur se trouve dans le Survivable Branch Appliance, le serveur Survivable Branch Server ou le serveur autonome Lync Server 2013 Standard ou serveur Enterprise Edition. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si le Survivable Branch Appliance devient indisponible, c’est ainsi que les clients de sites de succursale détecteront automatiquement le serveur d’inscriptions de sauvegarde.

Si un site de succursale ne dispose pas d’un serveur DNS, il existe deux alternatives pour configurer la découverte du Survivable Branch Appliance ou du serveur Survivable Branch Server :

  - Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de succursale de telle sorte qu’il pointe vers le nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server.

  - Configurez le Survivable Branch Appliance ou le serveur Survivable Branch Server de sorte qu’il réponde aux requêtes DHCP 120.

## Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau utilisateur pour les utilisateurs d’un site de succursale. Cette stratégie doit inclure un itinéraire principal, qui utilise le Survivable Branch Appliance ou la passerelle du serveur de succursale, ainsi qu’un ou plusieurs itinéraires alternatifs utilisant une jonction avec une passerelle RTC (réseau téléphonique commuté) au niveau du site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire alternatif faisant appel à une ou plusieurs passerelles de site central est utilisé à la place. Ainsi, quel que soit l’endroit où l’utilisateur est inscrit, soit sur le serveur d’inscriptions du site de succursale, soit sur le pool de serveurs d’inscriptions de sauvegarde du site central, la stratégie VoIP de l’utilisateur est toujours appliquée. Il est primordial de tenir compte de ce point pour les scénarios de basculement. Par exemple, si vous devez renommer le Survivable Branch Appliance ou reconfigurer le Survivable Branch Appliance poour le connecter à un pool de serveurs d’inscriptions de sauvegarde sur le site central, vous devez déplacer les utilisateurs du site de succursale vers le site central tout au long de l’opération. (Pour savoir comment renommer ou reconfigurer un Survivable Branch Appliance, reportez-vous à [Annexe B : Gestion d’un Survivable Branch Appliance dans Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) dans la documentation de déploiement.) Si ces utilisateurs ne disposent pas de stratégies VoIP ou de plans de numérotation au niveau utilisateur, lorsque les utilisateurs sont déplacés sur un autre site, les stratégies VoIP et les plans de numérotation au niveau du site central s’appliquent aux utilisateurs par défaut à la place des stratégies VoIP et des plans de numérotation au niveau du site de succursale. Dans ce scénario, leurs appels échoueront, à moins que les stratégies VoIP et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde puissent également s’appliquer aux utilisateurs du site de succursale. Par exemple, si les utilisateurs d’un site de succursale basé au Japon sont déplacés sur un site central situé à Redmond, il est probable qu’un plan de numérotation dont les règles de normalisation ajoutent le préfixe +1425 à tous les appels à 7 chiffres ne traduiront pas correctement les appels de ces utilisateurs.

> [!IMPORTANT]  
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique RTC à la stratégie utilisateur de succursale et d’affecter des itinéraires distincts à chacun d’entre eux. Le premier itinéraire, ou itinéraire principal, dirigerait les appels vers la passerelle associée au Survivable Branch Appliance (SBA) ou au serveur de succursale ; le deuxième itinéraire, ou itinéraire alternatif, dirigerait les appels vers la passerelle du site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires affectés au premier enregistrement d’utilisation RTC avant d’essayer le deuxième enregistrement.

Pour aider à s’assurer que les appels entrants destinés aux utilisateurs de site de succursale leur parviennent si la passerelle de succursale ou le composant Windows du site du Survivable Branch Appliance n’est pas disponible (par exemple, si le Survivable Branch Appliance ou la passerelle de succursale sont interrompus pour maintenance), créez un itinéraire de basculement sur la passerelle (ou collaborez avec votre fournisseur de sélection directe à l’arrivée) pour rediriger les appels entrants sur le pool de serveurs d’inscriptions de sauvegarde au niveau du site central. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. Assurez-vous que l’itinéraire convertit les numéros selon les formats de numéro de téléphone acceptés par la passerelle RTC ou un autre homologue de jonction. Pour plus d’informations sur la création d’un itinéraire de basculement, reportez-vous à [Configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous disposez de deux serveurs Survivable Branch Appliance sur un site de succursale, vous pouvez créer un plan de numérotation au niveau du site pour les deux, à moins qu’un plan distinct au niveau du service soit nécessaire pour chacun d’eux.

> [!NOTE]  
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, y compris les utilisateurs inscrits sur un Survivable Branch Appliance.

Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, reportez-vous à [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) et [Création de la stratégie de routage VoIP pour les utilisateurs de succursale dans Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) dans la documentation de déploiement.

## Acheminement des numéros de poste

Lors de la préparation des plans de numérotation et des stratégies de voix pour les utilisateurs d’un site de succursale, veillez à inclure des règles de normalisation et de conversion correspondant aux chaînes et au format de numéro utilisés dans l’attribut msRTCSIP-line (ou l’URI de ligne) afin que les appels Lync 2013 activés entre les utilisateurs du site de succursale et ceux du site central soient bien acheminés, notamment lorsqu’ils doivent être redirigés sur le réseau téléphonique commuté du fait de l’indisponibilité de la liaison de réseau étendu. D’autres éléments sont à prendre en considération dans le cas des numéros composés incluant des numéros de poste, et pas seulement des numéros de téléphone.

Les règles de normalisation et de conversion qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.

Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec *uniquement* un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Cependant, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.

Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour convertir le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :


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
<th>Nom de la règle</th>
<th>Description</th>
<th>Type de numéro</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Postes5chiffres</p></td>
<td><p>Ne convertit pas les numéros à 5 chiffres</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>$1</p></td>
<td><p>10001 n’est pas converti</p></td>
</tr>
</tbody>
</table>


Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. En cas de panne de réseau étendu, si l’utilisateur d’un site de succursale appelle un utilisateur du site central en composant uniquement le numéro de poste de ce dernier, vous devez disposer d’une règle de conversion sortante qui ajoute le numéro de téléphone complet de l’utilisateur du site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro de poste unique de l’utilisateur au lieu d’un numéro de téléphone complet propre à l’utilisateur, vous devez disposer d’une règle de conversion sortante qui ajoute le numéro de téléphone complet de l’organisation. Par exemple :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Modèle de correspondance</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Traduit les numéros à 5 chiffres en numéro de téléphone d’utilisateur avec numéro de poste</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550123;poste=$1</p></td>
<td><p>10001 devient +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Traduit les numéros à 5 chiffres en numéro de téléphone de votre organisation complété du poste d’un utilisateur</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550100;poste=$1</p></td>
<td><p>10001 devient +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de conversion sortante doit également supprimer le numéro de poste. Par exemple :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Modèle de correspondance</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Supprime le poste des numéros de téléphone présentant un numéro de poste</p></td>
<td><p>^\+(\d*);ext=(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 devient +14255550123</p></td>
</tr>
</tbody>
</table>


Qu’une liaison de réseau étendu soit disponible ou pas, si votre organisation n’a pas de numéros SDA configurés pour les utilisateurs individuels et que l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro de poste unique de l’utilisateur, vous devez configurer l’URI de ligne du numéro de téléphone de votre organisation avec un numéro joignable pour l’homologue de jonction ou la passerelle RTC du site de succursale. Vous devez également configurer l’URI de ligne du numéro de téléphone de votre organisation de sorte qu’il contienne son propre poste unique pour les appels devant être acheminés vers ce numéro.

Pour plus d’informations sur les appels d’un utilisateur de site central vers un utilisateur de site de succursale lorsque la liaison de réseau étendu entre les deux sites n’est pas disponible, reportez-vous à la section « Préparation à la survivabilité de la messagerie vocale » dans la suite de cette rubrique. Pour plus d’informations sur les plans de numérotation et les règles de normalisation et pour obtenir d’autres exemples de règles, reportez-vous à [Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification et [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md) dans la documentation de déploiement. Pour plus d’informations sur les règles de conversion sortante, reportez-vous à [Règles de conversion dans Lync Server 2013](lync-server-2013-translation-rules.md) dans la documentation de planification et [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.

## Préparation de la survavibilité de la messagerie vocale

La messagerie unifiée Exchange est généralement installée uniquement sur un site central, et non sur des sites de succursale. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. De ce fait, la configuration de l’URI de ligne pour le numéro de téléphone du standard automatique de la messagerie unifiée Exchange qui offre la messagerie vocale aux utilisateurs de site de succursale demande une attention particulière, tout comme la stratégie de voix, le plan de numérotation et les règles de normalisation applicables à ce numéro de messagerie vocale.

Les serveurs Survivable Branch Appliance (SBA) et les serveurs Survivable Branch Server assurent la survivabilité de la messagerie vocale pour les utilisateurs de succursale en cas de panne de réseau étendu. Plus précisément, si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server et que le réseau étendu devient indisponible, le SBA ou le serveur Survivable Branch Server réachemine les appels sans réponse sur le réseau téléphonique commuté vers la messagerie unifiée Exchange au niveau du site central. Avec un SBA ou un serveur Survivable Branch Server, les utilisateurs peuvent également récupérer des messages vocaux via le réseau téléphonique commuté en cas de panne de réseau étendu. Enfin, lors d’une panne de réseau étendu, le Survivable Branch Appliance ou le serveur Survivable Branch Server met en file d’attente les notifications d’appel manqué, puis les télécharge sur le serveur de la messagerie unifiée Exchange une fois le réseau étendu rétabli. Pour assurer la résistance du réacheminement de la messagerie vocale, veillez à ajouter une entrée pour le nom de domaine complet du pool du site central et une entrée pour le nom de domaine complet du serveur Edge dans le fichier d’hôtes du serveur Survivable Branch Server. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.

Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :

  - Un administrateur Microsoft Exchange doit configurer le standard automatique de la messagerie unifiée Exchange pour accepter les messages seulement. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.

  - L’administrateur Lync Server doit prendre le numéro de téléphone du standard automatique et l’utiliser comme numéro de **standard automatique de la messagerie unifiée Exchange** dans les paramètres de réacheminement de la messagerie vocale du Survivable Branch Appliance ou du serveur de succursale.

  - L’administrateur Lync Server doit obtenir le numéro de téléphone d’accès d’abonné de la messagerie unifiée Exchange et l’utiliser comme numéro d’**Accès abonné** dans les paramètres de réacheminement de la messagerie vocale du Survivable Branch Appliance ou du serveur Survivable Branch Server.

  - L’administrateur Lync Server doit configurer la messagerie unifiée Exchange de sorte qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursale qui ont besoin d’accéder à la messagerie vocale pendant une panne de réseau étendu.

  - Lorsque la liaison de réseau étendu n’est pas disponible, les appels à destination des utilisateurs de site de succursale peuvent être acheminés vers la messagerie vocale de la messagerie unifiée Exchange de l’utilisateur, à condition toutefois que la stratégie de voix appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et qu’elle inclue un numéro de poste.

## Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.

## Configuration requise pour les Survivable Branch Appliances

La configuration matérielle et logicielle requise est intégrée au Survivable Branch Appliance. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.

Si les serveurs DNS d’entreprise sont situés uniquement sur des sites centraux, les utilisateurs de sites de succursale ne seront pas en mesure de s’y connecter lors d’une panne de réseau étendu, et par conséquent la détection automatique Lync Server qui fait appel à un enregistrement de ressource de service (SRV) DNS échouera. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agir d’un serveur autonome ou d’une version du Survivable Branch Appliance qui prend en charge les fonctionnalités DNS. Pour plus d’informations, contactez votre fournisseur de Survivable Branch Appliance.

> [!NOTE]  
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. Le Survivable Branch Appliance authentifie les clients à l’aide d’un certificat spécial qu’il envoie au client à la signature en réponse à sa demande de certificat.

Les clients Lync peuvent détecter automatiquement Lync Server à l’aide du protocole DHCP, option 120 (option de serveur d’inscriptions SIP). La configuration peut prendre l’une des deux formes suivantes :

  - Configuration du serveur DHCP sur le site de succursale pour qu’il réponde aux requêtes DHCP 120, qui renvoient le nom de domaine complet du serveur d’inscriptions sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.

  - Activation du composant DHCP de Lync Server. Lorsque ce composant est activé, le serveur d’inscriptions Lync Server répond aux requêtes DHCP, option 120. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.

De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).

Pour finir, les utilisateurs de site de succursale doivent être configurés pour Voix Entreprise et disposer d’un point de terminaison de communications unifiées approprié.

## Configuration requise pour les serveurs Survivable Branch Server

La configuration requise pour les serveurs Survivable Branch Server est identique à celle de serveur frontal. Pour plus d’informations, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de planification.

## Conditions requise pour les déploiements de sites de succursale Lync Server pleine échelle

Pour plus d’informations, reportez-vous à [Définition de la configuration requise pour l’infrastructure pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.

