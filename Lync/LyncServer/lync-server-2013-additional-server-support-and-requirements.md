---
title: 'Lync Server 2013 : Autres prises en charge et configurations de serveur requises'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f2d1a1b728fcec84f0aed70f00f1143c70c490
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Autres prises en charge et configurations de serveur requises dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-12-09_

Outre la prise en charge logicielle décrite dans les autres sections de cette documentation sur la prise en charge, Lync Server 2013 présente les limites de support suivantes:

  - Lync Server 2013 prend en charge le système de nom de domaine (DNS) et l’équilibrage de charge matérielle pour des rôles de serveur spécifiques. Il prend également en charge l’équilibrage de charge des applications pour les serveurs de médiation, le cas échéant. Pour plus d’informations sur les situations d’utilisation, consultez la documentation de planification.

  - Lync Server 2013 utilise le protocole DLX (distribution de liste de distribution) pour développer des listes de distribution. Ce protocole spécifie également la méthode de service Web qui est utilisée pour obtenir l’appartenance d’une liste de distribution. Microsoft Exchange Server prend en charge les groupes dynamiques qui n’ont pas de membres attribués de manière statique. Au lieu de cela, il stocke les requêtes évaluées lors du développement du groupe. DLX ne prend pas en charge les listes de distribution dynamiques. Cette limitation DLX s’applique à toutes les versions de Lync Server.

  - L’Assistant permettre aux utilisateurs ne prenant pas en charge la conversion automatique des caractères non anglais en un URI compatible SIP, vous devez modifier manuellement l’adresse SIP.

  - Pour les serveurs exécutant un logiciel antivirus, voir exclusions de [l’analyse antivirus pour Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) pour les exclusions de virus proposées et autres recommandations en matière de sécurité.

  - Si vous utilisez IPsec, nous vous recommandons de désactiver IPsec par rapport aux plages de port utilisées pour le trafic audio et vidéo. Pour plus d’informations, reportez-vous à la section [exceptions IPSec dans Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.

  - Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure. Pour plus d’informations sur l’implémentation de QoS, voir [gestion de la qualité de service (QoS) dans Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) dans la documentation des opérations.

  - L’utilisation du pare-feu du système d’exploitation est prise en charge. Lync Server 2013 gère les exceptions de pare-feu pour le pare-feu du système d’exploitation, à l’exception du logiciel de base de données Microsoft SQL Server. Pour plus d’informations sur la configuration requise pour le pare-feu SQL Server, voir la documentation SQL Server.

  - Les interfaces externes utilisées pour mettre en œuvre la prise en charge de l’accès des utilisateurs externes doivent se trouver sur un sous-réseau distinct et *non* sur le même réseau que les interfaces internes.

  - La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

  - Avec la publication des mises à jour cumulatives de Lync Server 2013: juillet 2013, Lync Server 2013 prend désormais en charge l’authentification à deux facteurs. Pour plus d’informations, reportez-vous à la rubrique [authentification à deux facteurs dans Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La plupart des serveurs internes nécessitent un type de certificat défini comme **authentification d’ouverture** (OAuth). Vous devez demander et attribuer un certificat OAuth lors de la phase de **demande, d’installation et d’attribution des certificats** de l’Assistant Déploiement de Lync Server. La taille minimale d’une clé de certificat OAuth est de 1024 bits. Un avertissement risque de s’afficher si vous demandez un certificat dont la longueur de la clé est inférieure à 2048 bits. Pour éviter d’éventuels problèmes dans le cas où une longueur de clé de 2048 est appliquée au lieu d’être prévenu, il est vivement recommandé de toujours utiliser une longueur de clé d' 2048 pour les certificats OAuth.

  - Lync Server 2013 et Microsoft Exchange Server 2010 Service Pack 1 (SP1) prennent en charge les algorithmes 140-2 FIPS (Federal Information Processing Standard), si les systèmes d’exploitation Windows Server 2008 R2 sont configurés pour utiliser les algorithmes 140-2 FIPS pour cryptographie système. Pour mettre en œuvre la prise en charge du FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 pour le prendre en charge. Pour plus d’informations sur les algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du cryptage FIPS, voir l’article de la base de connaissances Microsoft 811833, «chiffrement de système: utiliser les algorithmes compatibles FIPS pour le paramètre de sécurité du chiffrement, du hachage et de la signature dans Windows XP et versions ultérieures. versions de Windows à [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)l’adresse. Pour plus d’informations sur la prise en charge et les limitations de FIPS 140-2 dans Exchange 2010, voir «Exchange 2010 SP1 et prise en [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)charge des algorithmes compatibles FIPS» à l’adresse.

Lync Server 2013 nécessite l’installation d’autres logiciels sur des composants spécifiques avant ou lors du déploiement. Cela inclut les logiciels disponibles avec le système d’exploitation, le logiciel téléchargeable et les logiciels qui sont automatiquement installés lors de l’installation de Lync Server 2013. Vous trouverez ci-dessous une liste de logiciels supplémentaires qui peuvent être nécessaires:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4,5 Framework

  - Microsoft Visual C++ 2012 redistribuable
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 redistribuable est automatiquement installé lors de l’installation de Lync Server 2013. Vous ne devez pas installer et utiliser une autre version.

    
    </div>

  - Module de réécriture d’URL version 2,0 redistribuable

  - Module d’exécution du format Windows Media

  - Windows PowerShell version 3,0

  - Plug-in Microsoft Silverlight 4 Browser (Silverlight 4.0.50524.0 ou la version la plus récente du panneau de configuration de Lync Server)

  - Outils de services de domaine Active Directory

Certaines de ces configurations logicielles s’appliquent uniquement aux rôles ou composants serveur spécifiques. Pour plus d’informations sur la configuration logicielle requise, voir [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

</div>

<span> </span>

</div>

</div>

</div>

