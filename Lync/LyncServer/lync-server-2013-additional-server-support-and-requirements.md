---
title: "Lync Server 2013 : Autres prises en charge et conf. de serveur requises"
TOCTitle: Autres prises en charge et configurations de serveur requises
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398577(v=OCS.15)
ms:contentKeyID: 49297771
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autres prises en charge et configurations de serveur requises dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Outre la prise en charge logicielle décrite dans les autres sections de cette documentation de prise en charge, Lync Server 2013 impose les restrictions suivantes en matière de prise en charge :

  - Lync Server 2013 prend en charge l’équilibrage de la charge DNS et de la charge matérielle pour des rôles serveur spécifiques. Il prend également en charge l’équilibrage de la charge d’application, le cas échéant. Pour plus d’informations pour sa² quand les utiliser, reportez-vous à la documentation de planification.

  - Lync Server 2013 utilise le protocole DLX (Distribution List Expansion) pour développer les listes de distribution. Ce protocole spécifie également la méthode de service web utilisée pour récupérer l’appartenance d’une liste de distribution. Microsoft Exchange Server prend en charge les groupes dynamiques auxquels aucun membre n’est attribué de manière statique. Au lieu de cela, ils stockent les demandes évaluées quand le groupe est développé. Le protocole DLX ne prend pas en charge les listes de distribution dynamiques.

  - L’Assistant Activer un utilisateur ne prend pas en charge la conversion automatique de caractères non anglais en URI compatible SIP, vous devez donc modifier l’adresse SIP manuellement.

  - Pour les serveurs exécutant un antivirus, reportez-vous à [Exclusions de l’analyse antivirus pour Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) pour consulter des suggestions d’exclusions de l’antivirus et d’autres recommandations relatives à la sécurité.

  - Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic audio et vidéo. Pour plus d’informations, reportez-vous à [Exceptions Ipsec dans Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.

  - Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure. Pour plus d’informations sur l’implémentation de la qualité de service, reportez-vous à [Gestion de la qualité de service (QoS)](lync-server-2013-managing-quality-of-service-qos.md) dans la documentation des opérations.

  - L’utilisation du pare-feu du système d’exploitation est prise en charge. Lync Server 2013 gère les exceptions du pare-feu du système d’exploitation, à l’exception du logiciel de base de données Microsoft SQL Server. Pour plus d’informations sur la configuration requise en matière de pare-feu SQL Server, reportez-vous à la documentation SQL Server.

  - Les interfaces externes utilisées pour implémenter la prise en charge de l’accès des utilisateurs externes doivent se trouver sur un sous-réseau distinct, et *pas* sur le même réseau que les interfaces internes.

  - La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tiers pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

  - Suite à la publication des mises à jour cumulatives de juillet 2013 pour Lync Server 2013, Lync Server 2013 prend désormais en charge l’authentification à deux facteurs. Pour plus d’informations, reportez-vous à [Planification et déploiement de l’authentification à deux facteurs](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La plupart des serveurs internes requièrent un type de certificat défini sur **Open Authentication** (OAuth). Vous devez demander et affecter un certificat OAuth pendant la phase **Demander, installer et affecter des certificats** de l’Assistant Déploiement de Lync Server. La taille minimale d’une clé de certificat OAuth s’élève à 1024 bits. Un avertissement peut s’afficher si vous demandez un certificat dont la longueur de clé est inférieure à 2048 bits. Pour éviter d’éventuels problèmes en cas d’application d’une longueur de clé de 2048 bits sans avertissement, il est fortement recommandé de toujours utiliser une longueur de clé de 2048 pour les certificats OAuth.

  - Lync Server 2013 et Microsoft Exchange Server 2010 Service Pack 1 (SP1) fonctionnent avec une prise en charge des algorithmes FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server 2008 R2 sont configurés pour utiliser les algorithmes FIPS 140-2 pour le chiffrement système. Pour permettre une prise en charge de la norme FIPS, vous devez configurer chaque serveur équipé de Lync Server 2013 pour que ce dernier puisse la reconnaître. Pour plus d’informations sur les algorithmes compatibles FIPS et la manière d’autoriser la prise en charge de cette norme, reportez-vous à l’article 811833 de la Base de connaissances Microsoft « Chiffrement système : utilisez des algorithmes compatibles FIPS pour le chiffrement, le hachage et la signature » dans Windows XP et les versions ultérieures de Windows à l’adresse <http://support.microsoft.com/kb/811833>. Pour plus d’informations sur la prise en charge des algorithmes FIPS 140-2 et des restrictions à cet égard dans Exchange 2010, reportez-vous à « Exchange 2010 SP1 et prise en charge des algorithmes compatibles FIPS » à l’adresse <http://go.microsoft.com/fwlink/?linkid=205335>.

Lync Server 2013 requiert l’installation d’autres logiciels sur des composants spécifiques avant et pendant le déploiement. Cela inclut les logiciels disponibles avec le système d’exploitation, les logiciels téléchargeables et les logiciels installés automatiquement pendant l’installation de Lync Server 2013. Voici une liste de logiciels supplémentaires pouvant s’avérer nécessaires :

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual C++ 2012 Redistributable
    
    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable s’installe automatiquement lorsque vous installez Lync Server 2013. Vous ne devez pas installer ni utiliser une autre version.

  - Module de réécriture d’URL version 2.0 Redistribuable

  - Module d’exécution du format Windows Media

  - Windows PowerShell version 3.0

  - Plug-in de navigateur Microsoft Silverlight 4 (Silverlight 4.0.50524.0 ou dernière version du Panneau de configuration Lync Server)

  - Outils services de domaine Active Directory

Certains de ces logiciels requis s’appliquent uniquement à des rôles serveur ou composants spécifiques. Pour plus d’informations sur ces logiciels requis, reportez-vous à [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

