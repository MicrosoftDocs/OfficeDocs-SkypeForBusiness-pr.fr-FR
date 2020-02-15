---
title: 'Lync Server 2013 : prise en charge et configuration requise pour les serveurs supplémentaires'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8eb02f0cf178807c656520787024d79ab0f09b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Prise en charge supplémentaire des serveurs et configuration requise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-09_

En plus de la prise en charge logicielle décrite dans les autres sections de cette documentation de prise en charge, Lync Server 2013 présente les limitations de prise en charge suivantes :

  - Lync Server 2013 prend en charge le système DNS (Domain Name System) et l’équilibrage de la charge matérielle pour des rôles serveur spécifiques. Il prend également en charge l’équilibrage de la charge d’application, le cas échéant. Pour plus d’informations pour savoir quand les utiliser, voir la documentation de planification.

  - Lync Server 2013 utilise le protocole DLX (distribution list expansion Protocol) pour développer les listes de distribution. Ce protocole spécifie également la méthode de service web utilisée pour récupérer l’appartenance d’une liste de distribution. Microsoft Exchange Server prend en charge les groupes dynamiques qui n’ont pas de membres attribués de façon statique. Au lieu de cela, ils stockent les demandes qui sont évaluées quand le groupe est développé. Le protocole DLX ne prend pas en charge les listes de distribution dynamiques. Cette limitation DLX s’applique à toutes les versions de Lync Server.

  - L’Assistant Activer un utilisateur ne prend pas en charge la conversion automatique de caractères non anglais en URI compatible SIP, vous devez donc modifier l’adresse SIP manuellement.

  - Pour les serveurs exécutant un logiciel antivirus, consultez la rubrique [exclusions d’analyse antivirus pour Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) pour obtenir les exclusions de virus suggérées et d’autres recommandations relatives à la sécurité.

  - Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic audio et vidéo. Pour plus d’informations, reportez-vous à la rubrique [IPSec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.

  - Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure. Pour plus d’informations sur l’implémentation de la qualité de service, consultez la rubrique [Managing Quality of service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) dans la documentation des opérations.

  - L’utilisation du pare-feu du système d’exploitation est prise en charge. Lync Server 2013 gère les exceptions de pare-feu pour le pare-feu du système d’exploitation, à l’exception du logiciel de base de données Microsoft SQL Server. Pour plus d’informations sur la configuration requise en matière de pare-feu SQL Server, voir la documentation SQL Server.

  - Les interfaces externes utilisées pour implémenter la prise en charge de l’accès des utilisateurs externes doivent se trouver sur un sous-réseau distinct, et *pas* sur le même réseau que les interfaces internes.

  - La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

  - Avec la publication des mises à jour cumulatives Lync Server 2013 : juillet 2013, Lync Server 2013 prend désormais en charge l’authentification à deux facteurs. Pour plus d’informations, reportez-vous à la rubrique [authentification à deux facteurs dans Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La plupart des serveurs internes nécessitent un type de certificat défini en tant qu' **authentification ouverte** (OAuth). Vous devez demander et affecter un certificat OAuth lors de la **demande, installer et affecter des certificats** de l’Assistant Déploiement de Lync Server. La taille minimale d’une clé de certificat OAuth est de 1024 bits. Un avertissement peut s’afficher si vous demandez un certificat dont la longueur de clé est inférieure à 2048 bits. Pour éviter des problèmes potentiels au cas où une longueur de clé de 2048 est appliquée au lieu d’être prévenu, il est vivement recommandé d’utiliser toujours une longueur de clé de 2048 pour les certificats OAuth.

  - Lync Server 2013 et Microsoft Exchange Server 2010 Service Pack 1 (SP1) fonctionnent avec la prise en charge des algorithmes FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server 2008 R2 sont configurés pour utiliser les algorithmes de la norme FIPS 140-2 pour chiffrement du système. Pour implémenter la prise en charge du cryptage FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 afin de le prendre en charge. Pour plus d’informations sur les algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du FIPS, consultez l’article 811833 de la base de connaissances Microsoft « chiffrement du système : utiliser des algorithmes compatibles FIPS pour le chiffrement, le hachage et la [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)signature » dans Windows XP et les versions ultérieures de Windows à l’adresse. Pour plus d’informations sur la prise en charge et les limitations du FIPS 140-2 dans Exchange 2010, voir « algorithmes de prise en charge [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)des algorithmes compatibles FIPS dans Exchange 2010 SP1 » à l’adresse.

Lync Server 2013 nécessite l’installation d’autres logiciels sur des composants spécifiques avant ou pendant le déploiement. Cela inclut les logiciels disponibles avec le système d’exploitation, les logiciels téléchargeables et les logiciels installés automatiquement lors de l’installation de Lync Server 2013. Voici une liste de logiciels supplémentaires pouvant s’avérer nécessaires :

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4,5 Framework

  - Microsoft Visual C++ 2012 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable est automatiquement installé lors de l’installation de Lync Server 2013. Vous ne devez pas installer et utiliser une autre version.

    
    </div>

  - Module de réécriture d’URL version 2.0 Redistribuable

  - Module d’exécution du format Windows Media

  - Windows PowerShell version 3,0

  - Plug-in de navigateur Microsoft Silverlight 4 (Silverlight 4.0.50524.0 ou dernière version du Panneau de configuration Lync Server)

  - Outils des services de domaine Active Directory

Certains de ces logiciels requis s’appliquent uniquement à des rôles serveur ou composants spécifiques. Pour plus d’informations sur la configuration logicielle requise, voir la rubrique relative à la [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

</div>

<span> </span>

</div>

</div>

</div>

