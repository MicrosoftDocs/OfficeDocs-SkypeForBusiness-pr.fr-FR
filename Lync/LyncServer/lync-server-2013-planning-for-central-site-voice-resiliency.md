﻿---
title: 'Lync Server 2013 : Planification de la résistance vocale du site central'
TOCTitle: Planification de la résistance vocale du site central
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398347(v=OCS.15)
ms:contentKeyID: 49297220
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la résistance vocale du site central dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. La gestion des services d’urgence, l’accès au support technique et la capacité à effectuer des tâches stratégiques pour l’entreprise quand un site central est hors service sont des éléments essentiels à toute solution de résistance Voix Entreprise. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :

  - Le basculement vocal doit être fourni.

  - Les utilisateurs qui s’inscrivent habituellement auprès du pool de serveurs frontaux du site central doivent pouvoir s’inscrire auprès d’un pool de serveurs frontaux de remplacement. Cela nécessite de créer plusieurs enregistrements DNS SRV, chacun d’entre eux devant être résolu en un pool de directeurs ou pool de serveurs frontaux sur chacun de vos sites centraux. Vous pouvez définir la priorité et le poids des enregistrements SRV pour que les utilisateurs servis par ce site central accèdent au directeur et au pool de serveurs frontaux avant ceux des autres enregistrements SRV.

  - Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.

Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.

## Architecture et topologie

La planification de la résistance vocale sur un site central nécessite de comprendre le rôle essentiel joué par le serveur d’inscriptions Lync Server 2013 dans l’activation du basculement vocal. Le serveur d’inscriptions Lync Server est un nouveau rôle serveur permettant l’inscription et l’authentification du client et fournissant des services de routage. Il se trouve avec les autres composants d’un serveur Standard Edition, serveur frontal, directeur ou Survivable Branch Appliance. Un pool de serveurs d’inscriptions se compose de services de serveur d’inscriptions exécutés sur le pool pool de serveurs frontaux et se trouvant sur le même site. La charge du pool pool de serveurs frontaux doit être équilibrée. L’équilibrage de la charge DNS est recommandé, mais l’équilibrage de la charge matérielle est acceptable. Un client Lync découvre le pool pool de serveurs frontaux via les mécanismes de découverte suivants :

1.  Enregistrement DNS SRV

2.  Service web de découverte automatique (nouveauté de Lync Server 2013)

3.  Option DHCP 120

Une fois que le client Lync se connecte au pool de serveurs frontaux, il est dirigé par l’équilibrage de charge vers l’un des serveurs frontaux du pool. Ce serveur frontal redirige à son tour le client vers un serveur d’inscriptions par défaut du pool.

Chaque utilisateur activé pour Voix Entreprise est affecté à un pool de serveurs d’inscriptions spécifique, qui devient son pool de serveurs d’inscriptions principal. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, dont les utilisateurs inscrits sur un Survivable Branch Appliance.

Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. Le pool de secours peut être configuré à l’aide des paramètres de résistance du Générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.

Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :

1.  Un client découvre Lync Server via les enregistrements DNS SRV. Dans Lync Server 2013, les enregistrements DNS SRV peuvent être configurés pour renvoyer plusieurs noms de domaine complets à la requête DNS SRV. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool directeur de l’un des sites est disponible, le client peut se connecter au premier tronçon Lync Server.
    
    > [!NOTE]  
    > L’utilisation d’un pool de directeurs est facultative. Il est possible d’utiliser un pool de serveurs frontaux à la place.

2.  Le pool de directeurs informe le client Lync de la présence du pool de serveurs d’inscriptions principal de l’utilisateur et du pool de serveurs d’inscriptions de sauvegarde.

3.  Le client Lync tente d’abord de se connecter au pool de serveurs d’inscriptions principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool de serveurs d’inscriptions principal n’est pas disponible, le client Lync tente de se connecter au pool de serveurs d’inscriptions de sauvegarde. Si le pool de serveurs d’inscriptions de sauvegarde est disponible et a déterminé que le pool de serveurs d’inscriptions principal de l’utilisateur est indisponible (en détectant un manque de pulsations pendant l’intervalle de basculement spécifié), le pool de serveurs d’inscriptions de sauvegarde accepte l’inscription de l’utilisateur. Quand le serveur d’inscriptions de sauvegarde détecte que le serveur d’inscriptions principal est de nouveau disponible, le pool de serveurs d’inscriptions de sauvegarde redirige les clients Lync de basculement vers leur pool principal.

La figure suivante présente la topologie recommandée pour la résistance du site central. Les deux sites sont connectés par une liaison réseau étendu résistante. Si le site central devient indisponible, les utilisateurs affectés à ce pool sont dirigés vers le site de sauvegarde pour l’inscription.

**Topologie recommandée pour la résistance vocale du site central**

![Topologie pour la résilience vocale du site central](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie pour la résilience vocale du site central")

## Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :

  - Les sites où se trouvent les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.

  - Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.

  - La charge de chaque pool de serveurs d’inscriptions doit être équilibrée via l’équilibrage de la charge DNS, l’équilibrage de la charge matérielle ou les deux. Pour plus d’informations sur la planification de votre configuration d’équilibrage de la charge, reportez-vous à [Configuration requise pour l’équilibrage de charge dans Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Chaque utilisateur doit être affecté à un pool de serveurs d’inscriptions principal à l’aide de l’applet de commande Lync Server Management Shell**set-CsUser** ou du Panneau de configuration Lync Server.

  - Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.

  - Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde après 300 secondes. Vous pouvez modifier cette durée à l’aide du générateur de topologie de Lync Server 2013.

  - Configurez un itinéraire de basculement comme décrit à la rubrique « [Configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md) » de la documentation de planification. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.

  - Si le site central contient votre serveur de gestion principal et qu’il est susceptible d’être indisponible pendant une longue période, vous devez réinstaller vos outils de gestion sur le site de sauvegarde ; sinon, vous ne pourrez pas modifiez vos paramètres de gestion.

## Dépendances

Lync Server dépend des composants logiciels et d’infrastructure suivants pour garantir la résistance vocale :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Composant</strong></p></td>
<td><p><strong>Fonction</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Résolution des enregistrements SRV et des enregistrements A pour la connectivité serveur-serveur et serveur-client</p></td>
</tr>
<tr class="odd">
<td><p>Exchange et services web Exchange (EWS)</p></td>
<td><p>Stockage des contacts ; données de calendrier</p></td>
</tr>
<tr class="even">
<td><p>Messagerie unifiée Exchange et services web Exchange</p></td>
<td><p>Journaux des appels, liste des messages vocaux, messagerie vocale</p></td>
</tr>
<tr class="odd">
<td><p>Options DHCP 120</p></td>
<td><p>Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions. Pour ce faire, vous devez soit configurer un serveur DHCP, soit activer le protocole DHCP de Lync Server 2013. Pour plus d’informations, reportez-vous à la description de la configuration matérielle et logicielle requise pour la résistance du site de succursale, dans la section <a href="lync-server-2013-branch-site-resiliency-requirements.md">Configuration requise pour la résistance des sites de succursale pour Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


## Fonctionnalités vocales de secours

Si les conditions et recommandations précédentes ont été implémentées, les fonctionnalités vocales suivantes seront fournies par le pool de serveurs d’inscriptions :

  - Appels RTC sortants

  - Appels RTC entrants si le fournisseur de services de téléphonie prend en charge le basculement vers un site de sauvegarde

  - Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

  - Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

  - Messagerie instantanée entre deux utilisateurs et partage audio et vidéo entre des utilisateurs situés sur le même site

  - Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si les deux parties utilisant la délégation d’appel, ou tous les membres de l’équipe, sont configurés sur le même site.

  - Les téléphones et clients existants continuent à fonctionner.

  - Enregistrement des détails des appels (CDR)

  - Authentification et autorisation

En fonction de leur configuration, les fonctionnalités vocales suivantes fonctionneront ou ne fonctionneront pas lors de la mise hors service d’un site central principal :

  - Dépôt et récupération de messages vocaux
    
    Si vous souhaitez que la messagerie unifiée Exchange soit disponible lorsque le site central principal est hors service, effectuez l’une des opérations suivantes :
    
      - Modifiez les enregistrements DNS SRV pour que les serveurs de messagerie unifiée Exchange situés sur le site central pointent sur les serveurs de messagerie unifiée Exchange de sauvegarde situés sur un autre site.
    
      - Configurez le plan de numérotation de messagerie unifiée Exchange de chaque utilisateur pour inclure les serveurs de messagerie unifiée Exchange sur le site central et le site de sauvegarde, mais définissez les serveurs de messagerie unifiée Exchange de sauvegarde comme désactivés. Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs de messagerie unifiée Exchange du site de sauvegarde comme activés.
    
    Si aucune des solutions précédentes n’est possible, la messagerie unifiée Exchange ne sera pas disponible si le site central devient indisponible.

  - Conférence de tous types
    
    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, les autres utilisateurs ne peuvent pas participer aux conférences hébergées sur le pool principal de l’utilisateur concerné.

Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :

  - standard automatique de conférence

  - Routage basé sur la présence et DND

  - Mise à jour des paramètres de transfert d’appel

  - Service Response Group et parcage d’appel

  - Provisionnement des nouveaux téléphones et clients

  - Recherche web du carnet d’adresses

## Voir aussi

#### Autres ressources

[Planification de la résistance vocale d’un site de succursale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

