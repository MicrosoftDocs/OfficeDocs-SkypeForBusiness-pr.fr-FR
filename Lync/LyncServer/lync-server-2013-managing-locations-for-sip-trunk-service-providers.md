---
title: "Lync Server 2013 : Gest. des empl. pour les fourn. de service de jonction SIP"
TOCTitle: Gestion des emplacements pour les fournisseurs de service de jonction SIP
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398959(v=OCS.15)
ms:contentKeyID: 49299046
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des emplacements pour les fournisseurs de service de jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour configurer Lync Server afin de rechercher automatiquement les clients sur un réseau, vous devez ajouter un schéma de câblage réseau dans la base de données du service d’informations sur l’emplacement et publier les emplacements, ou définir un lien vers une base de données externe qui contient déjà les mappages appropriés. Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1. Pour plus d’informations, reportez-vous à [Configurer la base de données d’emplacements dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.

Vous renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment. Le champ **Location** du service d’informations sur l’emplacement (emplacement spécifique au sein d’un bâtiment) a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

  - Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

  - Identificateur d’emplacement qui aide les utilisateurs à vérifier que leur client Lync a sélectionné l’emplacement correct. Le client Lync concatène et affiche automatiquement les champs **Location** et **City** découverts dans son en-tête. Il est recommandé d’ajouter l’adresse postale de l’immeuble à chaque identificateur d’emplacement (par exemple, « 1er étage \<numéro de rue\> »). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

  - Si l’emplacement est approximatif (car déterminé par un point d’accès sans fil), vous pouvez ajouter le mot Near (par exemple, « À proximité du 1er étage 1234 »).

> [!NOTE]  
> Les emplacements ajoutés à la base de données centrale des emplacements ne sont accessibles au client qu’une fois publiés à l’aide d’une commande Lync Server Management Shell et répliqués vers les magasins locaux du pool. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-the-location-database.md">Publier la base de données d’emplacements</a> dans la documentation de déploiement.

Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.

## Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.

  - **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**  
    Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?

<!-- end list -->

  - **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**  
    En utilisant l’option du service d’informations sur l’emplacement secondaire de Lync Server pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors ligne. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Par conséquent, le service d’informations sur l’emplacement peut renvoyer plusieurs adresses provenant du service d’informations sur l’emplacement vers un client Lync Server. L’utilisateur peut alors choisir l’emplacement le plus approprié.
    
    Pour permettre l’intégration au service d’informations sur l’emplacement, la base de données tierce doit respecter le schéma Demande/Réponse d’emplacement de Lync Server. Pour plus d’informations, reportez-vous à « \[MS-E911WS\] : service web pour la spécification de protocole de prise en charge E911 » à l’adresse <http://go.microsoft.com/fwlink/p/?linkid=213819>. Pour plus d’informations sur le déploiement d’un service d’informations sur l’emplacement secondaire, reportez-vous à [Configurer un service Informations d’emplacement secondaire](lync-server-2013-configure-a-secondary-location-information-service.md) dans la documentation de déploiement.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, reportez-vous à [Configurer la base de données d’emplacements dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.

## Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

  - **Comment allez-vous mettre à jour la base de données d’emplacements ?**  
    L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

<!-- end list -->

  - **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**  
    Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP de châssis ou un ID de port qui ne figure pas dans la base de données, le service d’informations sur l’emplacement ne pourra pas renvoyer un emplacement au client.

