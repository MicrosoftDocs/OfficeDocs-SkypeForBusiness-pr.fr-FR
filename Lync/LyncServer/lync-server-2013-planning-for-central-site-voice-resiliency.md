---
title: 'Lync Server 2013 : planification de la résistance vocale du site central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af584c5a9ff1e061594ab5956b54032d56cd4ae4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planification de la résistance vocale du site central dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-30_

De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier. La maintenance des services d’urgence, l’accès au support technique et la possibilité d’effectuer des tâches professionnelles critiques lorsqu’un site central est inaccessible sont essentielles pour toute solution de résistance vocale d’entreprise. Quand un site central devient indisponible, les conditions suivantes doivent être remplies :

  - Le basculement vocal doit être fourni.

  - Les utilisateurs qui s’inscrivent généralement auprès du pool frontal sur le site central doivent être en mesure de s’inscrire auprès d’un autre pool frontal. Pour ce faire, vous pouvez créer plusieurs enregistrements SRV DNS, chacun d’eux résolu en un pool directeur ou un pool frontal dans chacun de vos sites centraux. Vous pouvez ajuster la priorité et les pondérations des enregistrements SRV afin que les utilisateurs qui sont pris en charge par ce site central obtiennent le directeur et le pool frontal correspondants avant ceux d’autres enregistrements SRV.

  - Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.

Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.

<div>

## <a name="architecture-and-topology"></a>Architecture et topologie

La planification de la résistance des communications vocales dans un site central nécessite une connaissance de base du rôle central joué par le serveur d’inscriptions Lync Server 2013 pour activer le basculement vocal. Le serveur d’inscriptions Lync Server est un rôle de serveur qui permet l’enregistrement et l’authentification du client et fournit des services de routage. Il réside avec d’autres composants sur un serveur Standard Edition, un serveur frontal, un directeur ou un Survivable Branch appliance. Un pool de serveurs d’inscriptions se compose de services de serveur d’inscriptions s’exécutant sur le pool frontal et résidant sur le même site. Le pool frontal doit être équilibré en charge. L’équilibrage de la charge DNS est recommandé, mais l’équilibrage de la charge matérielle est acceptable. Un client Lync Découvre le pool frontal via le mécanisme de découverte suivant :

1.  Enregistrement DNS SRV

2.  Service Web de découverte automatique (nouveau dans Lync Server 2013)

3.  Option DHCP 120

Une fois que le client Lync se connecte au pool frontal, il est dirigé par l’équilibreur de charge vers l’un des serveurs frontaux du pool. Ce serveur frontal, à son tour, redirige le client vers un serveur d’inscriptions préféré dans le pool.

Chaque utilisateur activé pour voix entreprise est affecté à un pool de serveurs d’inscriptions particulier, qui devient le pool de serveurs d’inscriptions principal de cet utilisateur. Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal. Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, y compris les utilisateurs enregistrés avec un Survivable Branch appliance.

Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site. La sauvegarde peut être configurée à l’aide des paramètres de résistance du générateur de topologie. S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.

Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :

1.  Un client identifie Lync Server par le biais des enregistrements SRV DNS. Dans Lync Server 2013, les enregistrements DNS SRV peuvent être configurés pour renvoyer plus d’un nom de domaine complet à la requête SRV DNS. Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites. Tant que le pool directeur de l’un des emplacements est disponible, le client peut se connecter au premier tronçon Lync Server.
    
    <div>
    

    > [!NOTE]  
    > L’utilisation d’un pool directeur est facultative. Un pool frontal peut être utilisé à la place.

    
    </div>

2.  Le pool Directeur informe le client Lync sur le pool de serveurs d’inscriptions principal de l’utilisateur et le pool de serveurs d’inscriptions de sauvegarde.

3.  Le client Lync tente d’abord de se connecter au pool de serveurs d’inscriptions principal de l’utilisateur. Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription. Si le pool de serveurs d’inscriptions principal n’est pas disponible, le client Lync tente de se connecter au pool de serveurs d’inscriptions de sauvegarde. Si le pool de serveurs d’inscriptions de sauvegarde est disponible et a déterminé que le pool de serveurs d’inscriptions principal de l’utilisateur est indisponible (en détectant un manque de pulsations pendant l’intervalle de basculement spécifié), le pool de serveurs d’inscriptions de sauvegarde accepte l’inscription de l’utilisateur. Une fois que le serveur d’inscriptions de sauvegarde détecte que le serveur d’inscriptions principal est de nouveau disponible, le pool de serveurs d’inscriptions de sauvegarde redirige les clients Lync de basculement vers leur pool principal.

La figure suivante présente la topologie recommandée pour la résistance du site central. Les deux sites sont connectés par une liaison réseau étendu résistante. Si le site central devient indisponible, les utilisateurs qui sont affectés à ce pool sont dirigés vers le site de sauvegarde pour l’inscription.

**Topologie recommandée pour la résistance vocale du site central**

![Topologie pour les communications vocales du site la résilience](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie pour les communications vocales du site la résilience")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :

  - Les sites où résident les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.

  - Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.

  - La charge de chaque pool de serveurs d’inscriptions doit être équilibrée à l’aide de l’équilibrage de charge DNS, de l’équilibrage de charge matérielle ou des deux. Pour plus d’informations sur la planification de votre configuration d’équilibrage de charge, voir [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Chaque utilisateur doit être affecté à un pool de serveurs d’inscriptions principal à l’aide de la cmdlet **Set-Csuser** de Lync Server Management Shell ou du panneau de configuration Lync Server.

  - Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.

  - Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde. Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde au bout de 300 secondes. Vous pouvez modifier cet intervalle à l’aide du générateur de topologies Lync Server 2013.

  - Configurez un itinéraire de basculement, comme décrit dans la rubrique «[configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)» dans la documentation de planification. Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.

  - Si le site central contient votre serveur de gestion principal et qu’il est susceptible d’être indisponible pendant une longue période, vous devez réinstaller vos outils de gestion sur le site de sauvegarde ; sinon, vous ne pourrez pas modifiez vos paramètres de gestion.

</div>

<div>

## <a name="dependencies"></a>Dépendances

Lync Server dépend des composants logiciels et d’infrastructure suivants pour garantir la résistance vocale :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Composant</strong></p></td>
<td><p><strong>Dysfonctionnement</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Résolution des enregistrements SRV et des enregistrements A pour la connectivité serveur-serveur et serveur-client</p></td>
</tr>
<tr class="odd">
<td><p>Exchange et services Web Exchange (EWS)</p></td>
<td><p>Stockage des contacts ; données de calendrier</p></td>
</tr>
<tr class="even">
<td><p>Messagerie unifiée Exchange et services Web Exchange</p></td>
<td><p>Journaux des appels, liste des messages vocaux, messagerie vocale</p></td>
</tr>
<tr class="odd">
<td><p>Options DHCP 120</p></td>
<td><p>Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions. Pour que cela fonctionne, un serveur DHCP doit être configuré ou Lync Server 2013 DHCP doit être activé. Pour plus d’informations, voir Configuration matérielle et logicielle requise pour la résistance des sites de succursale dans la section <a href="lync-server-2013-branch-site-resiliency-requirements.md">Configuration requise pour la résistance des sites de succursale pour Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Fonctionnalités vocales de secours

Si les conditions et recommandations précédentes ont été implémentées, les fonctionnalités vocales suivantes seront fournies par le pool de serveurs d’inscriptions :

  - Appels PSTN sortants

  - Appels PSTN entrants si le fournisseur de services de téléphonie prend en charge le basculement vers un site de sauvegarde

  - Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

  - Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

  - Messagerie instantanée entre deux utilisateurs, et partage audio et vidéo entre des utilisateurs situés sur le même site

  - Services de transfert d’appel, de sonnerie simultanée des systèmes d’extrémité, de délégation d’appel et d’appel d’équipe, mais seulement si les deux parties utilisant la délégation d’appel, ou tous les membres de l’équipe, sont configurés sur le même site.

  - Les téléphones et clients existants continuent à fonctionner.

  - Enregistrement des détails des appels (CDR)

  - Authentification et autorisation

En fonction de leur configuration, les fonctionnalités vocales suivantes fonctionneront ou ne fonctionneront pas lors de la mise hors service d’un site central principal :

  - Dépôt et récupération de messages vocaux
    
    Si vous souhaitez que la messagerie unifiée Exchange soit disponible lorsque le site central principal est hors service, effectuez l’une des opérations suivantes :
    
      - Modifiez les enregistrements DNS SRV pour que les serveurs de messagerie unifiée Exchange situés sur le site central pointent sur les serveurs de messagerie unifiée Exchange de sauvegarde situés sur un autre site.
    
      - Configurez le plan de numérotation de messagerie unifiée Exchange de chaque utilisateur pour inclure les serveurs de messagerie unifiée Exchange sur le site central et le site de sauvegarde, mais désignez-le comme désactivé. Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs de messagerie unifiée Exchange sur le site de sauvegarde comme étant activé.
    
    Si aucune des solutions précédentes n’est possible, la messagerie unifiée Exchange ne sera pas disponible si le site central devient indisponible.

  - Conférence de tous types
    
    Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, les autres utilisateurs ne peuvent pas participer aux conférences qui sont hébergées sur le pool principal de l’utilisateur concerné.

Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :

  - standard automatique de conférence

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

