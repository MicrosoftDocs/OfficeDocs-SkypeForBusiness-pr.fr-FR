---
title: 'Lync Server 2013 : gestion des emplacements pour les fournisseurs de service SIP Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ebc471459c8e406914f5a075d7e4cf8b69fadd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Gestion des emplacements pour les fournisseurs de services SIP Trunk dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Pour configurer Lync Server de façon à ce qu’il détecte automatiquement les clients au sein d’un réseau, vous devez renseigner la base de données de service informations d’emplacement auprès d’un Wiremap réseau et publier les emplacements, ou lier une base de données externe contenant déjà le bon mappages. Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1. Pour plus d’informations, reportez-vous à [la rubrique Configurer la base de données de localisation dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.

Renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment. Le champ d' **emplacement** du service des informations d’emplacement, qui correspond à un emplacement spécifique au sein d’un immeuble, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

  - Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

  - Un identificateur d’emplacement qui permet à l’utilisateur de voir facilement le bon emplacement du client Lync. Le client Lync concatène et affiche automatiquement les champs **emplacement** et **ville** détectés dans son en-tête. Il est recommandé d’ajouter l’adresse postale du bâtiment à chaque identificateur d’emplacement (par exemple, « numéro \<\>de rue du 1er étage »). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

  - Si l’emplacement est approximatif (car déterminé par un point d’accès sans fil), vous pouvez ajouter le mot Near (par exemple, « À proximité du 1er étage 1234 »).

<div>


> [!NOTE]  
> Les emplacements ajoutés à la base de données d’emplacement central ne sont pas disponibles pour le client tant qu’ils n’ont pas été publiés à l’aide d’une commande Lync Server Management Shell et répliqués dans les boutiques locales du pool. Pour plus d’informations, voir <A href="lync-server-2013-publish-the-location-database.md">publier la base de données de localisation à partir de Lync Server 2013</A> dans la documentation de déploiement.



</div>

Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.

<div>

## <a name="populating-the-location-database"></a>Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.

  - **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**  
    Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?

<!-- end list -->

  - **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**  
    À l’aide de l’option de service d’information d’emplacement secondaire du serveur Lync Server pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors connexion. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Cela signifie que le service d’information d’emplacement peut retourner plusieurs adresses à partir du service d’information d’emplacement secondaire, vers un client serveur Lync. L’utilisateur peut alors choisir l’emplacement le plus approprié.
    
    Pour être intégré au service d’information d’emplacement, la base de données tierce doit suivre le schéma de requête/réponse d’emplacement du serveur Lync. Pour en savoir plus,\[voir « MS\]-E911WS : Web service for E911 support Protocol Specification <http://go.microsoft.com/fwlink/p/?linkid=213819>» à l’adresse. Pour plus d’informations sur le déploiement d’un service d’information d’emplacement secondaire, voir [configurer un service d’information d’emplacement secondaire dans Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) dans la documentation de déploiement.

Pour plus d’informations sur le remplissage de la base de données de localisation, voir [configurer la base de données de localisation dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

  - **Comment allez-vous mettre à jour la base de données d’emplacements ?**  
    L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

<!-- end list -->

  - **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**  
    Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP du châssis ou un ID de port qui n’est pas inclus dans la base de données, le service d’information d’emplacement n’est pas en mesure de renvoyer un emplacement au client.

</div>

</div>

<span> </span>

</div>

</div>

</div>

