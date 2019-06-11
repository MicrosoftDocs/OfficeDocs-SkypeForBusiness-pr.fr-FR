---
title: 'Lync Server 2013 : Planification de la résistance vocale du site central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planification de la résistance vocale du site central dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-30_

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. La mise à jour des services d’urgence, l’accès au support technique et la possibilité d’effectuer des tâches professionnelles critiques quand un site central est hors service est essentiel pour toute solution de résilience vocale d’entreprise. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :

  - Le basculement vocal doit être fourni.

  - Les utilisateurs qui s’inscrivent habituellement avec le pool frontal sur le site central doivent pouvoir s’inscrire avec un autre pool frontal. Pour ce faire, vous pouvez créer plusieurs enregistrements SRV DNS, chacun d’eux résolu vers un pool de directeurs ou un pool frontal dans chacun de vos sites centraux. Vous pouvez ajuster la priorité et le poids des enregistrements SRV de telle sorte que les utilisateurs qui sont servis par ce site central obtiennent le directeur et la liste frontale correspondants dans d’autres enregistrements SRV.

  - Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.

Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.

<div>

## <a name="architecture-and-topology"></a>Architecture et topologie

La planification de la résilience vocale sur un site central nécessite une connaissance de base du rôle central joué par le Bureau d’enregistrement 2013 du serveur Lync en activant le basculement sur voix. Lync Server Registrar est un rôle serveur qui permet l’inscription et l’authentification du client et fournit les services de routage. Il se trouve avec d’autres composants sur un serveur Standard Edition, un serveur frontal, un directeur ou une branche Survivable. Un pool d’bureaux d’enregistrement est constitué de services d’enregistrement de registre en cours d’exécution sur le pool frontal et résidant sur le même site. Le pool frontal doit être équilibré. L’équilibrage de charge DNS est recommandé, mais l’équilibrage de charge matérielle est acceptable. Un client Lync Découvre le pool frontal par le biais du mécanisme de découverte suivant:

1.  Enregistrement DNS SRV

2.  Service Web de découverte automatique (nouveau dans Lync Server 2013)

3.  Option DHCP 120

Lorsque le client Lync se connecte au pool frontal, il est dirigé par le biais de l’équilibrage de charge vers l’un des serveurs frontaux de la liste. Ce serveur frontal, à son tour, redirige le client vers un bureau d’enregistrement préféré dans le pool.

Chaque utilisateur activé pour voix entreprise est attribué à un pool d’bureaux d’enregistrement particulier, lequel devient le pool d’inscriptions principal de cet utilisateur. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite sur le nombre d’utilisateurs de sites de succursales, y compris les utilisateurs enregistrés auprès d’une unité de succursale Survivable.

Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. La sauvegarde peut être configurée à l’aide des paramètres de résilience du générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.

Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :

1.  Un client Découvre Lync Server via les enregistrements DNS SRV. Dans Lync Server 2013, les enregistrements DNS SRV peuvent être configurés pour renvoyer plusieurs FQDN vers la requête DNS SRV. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool de directeurs dans l’un des emplacements est disponible, le client peut se connecter au premier serveur Lync tronçon.
    
    <div>
    

    > [!NOTE]  
    > L’utilisation d’un pool de directeurs est facultative. Un pool frontal peut être utilisé à la place.

    
    </div>

2.  Le pool de répertoires informe le client Lync sur le pool d’inscriptions principal de l’utilisateur et le pool d’inscriptions de sauvegarde.

3.  Le client Lync tente d’abord de se connecter au pool d’inscriptions principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool d’inscriptions principal n’est pas disponible, le client Lync tente de se connecter au pool d’inscriptions de sauvegarde. Si le pool de serveurs d’inscriptions de sauvegarde est disponible et a déterminé que le pool de serveurs d’inscriptions principal de l’utilisateur est indisponible (en détectant un manque de pulsations pendant l’intervalle de basculement spécifié), le pool de serveurs d’inscriptions de sauvegarde accepte l’inscription de l’utilisateur. Après que le Bureau d’enregistrement de la sauvegarde a détecté que le Bureau d’enregistrement principal est de nouveau disponible, le pool d’inscriptions de sauvegarde redirigera les clients Lync de basculement vers leur pool principal.

La figure suivante illustre la topologie recommandée pour garantir la résilience du site central. Les deux sites sont connectés à l’aide d’une liaison réseau étendu fiable. Si le site central devient indisponible, les utilisateurs qui sont affectés à ce pool sont dirigés vers le site de sauvegarde pour inscription.

**Topologie recommandée pour la résilience vocale d’un site central**

![Topologie pour les appels vocaux de site resliency] (images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie pour les appels vocaux de site resliency")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :

  - Les sites où se trouvent les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.

  - Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.

  - La charge de chaque pool de serveurs d’inscriptions doit être équilibrée via l’équilibrage de la charge DNS, l’équilibrage de la charge matérielle ou les deux. Pour plus d’informations sur la planification de la configuration de l’équilibrage de charge, voir [Configuration requise pour l’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Chaque utilisateur doit être affecté à un pool d’inscriptions principal en utilisant l’applet **de commande Set-Csuser** de Lync Server Management Shell ou le panneau de configuration de Lync Server.

  - Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.

  - Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde après 300 secondes. Vous pouvez modifier cet intervalle à l’aide du générateur de topologie Lync Server 2013.

  - Configurez un itinéraire de basculement, comme décrit dans la rubrique «[configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)» de la documentation de planification. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.

  - Si le site central contient votre serveur de gestion principal et qu’il est susceptible d’être indisponible pendant une longue période, vous devez réinstaller vos outils de gestion sur le site de sauvegarde ; sinon, vous ne pourrez pas modifier vos paramètres de gestion.

</div>

<div>

## <a name="dependencies"></a>Dépendances

Le serveur Lync dépend de l’infrastructure et des composants logiciels suivants pour garantir la résilience vocale:


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
<td><p>Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions. Pour que cette opération fonctionne, un serveur DHCP doit être configuré ou le protocole DHCP Lync Server 2013 doit être activé. Pour plus d’informations, consultez la configuration matérielle et logicielle requise pour la résilience de site pour les filiales dans la section Configuration de la résilience de <a href="lync-server-2013-branch-site-resiliency-requirements.md">site pour Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Fonctionnalités vocales de secours

Si les conditions et recommandations précédentes ont été implémentées, les fonctionnalités vocales suivantes seront fournies par le pool de serveurs d’inscriptions :

  - Appels RTC sortants

  - Appels RTC entrants si le fournisseur de services de téléphonie prend en charge le basculement vers un site de sauvegarde

  - Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

  - Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

  - Messagerie instantanée entre deux utilisateurs et partage audio et vidéo entre des utilisateurs situés sur le même site

  - Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si les deux parties utilisant la délégation d’appel (ou tous les membres de l’équipe) sont configurés sur le même site.

  - Les téléphones et clients existants continuent à fonctionner.

  - Enregistrement des détails des appels (CDR)

  - Authentification et autorisation

En fonction de leur configuration, les fonctionnalités vocales suivantes fonctionneront ou ne fonctionneront pas lors de la mise hors service d’un site central principal :

  - Dépôt et récupération de messages vocaux
    
    Si vous souhaitez que la messagerie unifiée Exchange soit disponible lorsque le site central principal est hors service, effectuez l’une des opérations suivantes :
    
      - Modifiez les enregistrements DNS SRV pour que les serveurs de messagerie unifiée Exchange situés sur le site central pointent sur les serveurs de messagerie unifiée Exchange de sauvegarde situés sur un autre site.
    
      - Configurez le plan de numérotation de messagerie unifiée Exchange de chaque utilisateur de manière à inclure les serveurs de messagerie unifiée Exchange à la fois sur le site central et sur le site de sauvegarde, mais définissez les serveurs de messagerie unifiée Exchange Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs Exchange UM sur le site de sauvegarde comme activé.
    
    Si aucune des solutions précédentes n’est possible, la messagerie unifiée Exchange ne sera pas disponible dans l’éventualité où le site central ne sera pas disponible.

  - Conférence de tout type
    
    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, les autres utilisateurs ne peuvent pas participer aux conférences hébergées sur le pool principal de l’utilisateur concerné.

Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :

  - Standard automatique de conférence

  - Routage basé sur la présence et DND

  - Mise à jour des paramètres de transfert d’appel

  - Service Response Group et parcage d’appel

  - Provisionnement des nouveaux téléphones et clients

  - Recherche web du carnet d’adresses

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la résistance vocale d’un site de succursale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

