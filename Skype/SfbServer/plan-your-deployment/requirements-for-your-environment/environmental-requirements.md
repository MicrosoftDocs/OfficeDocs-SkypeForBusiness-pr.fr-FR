---
title: Configuration environnementale requise pour Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Résumé : configurez votre configuration non-serveur requise pour Skype entreprise Server 2015. Vous souhaiterez peut-être configurer un grand nombre d’éléments avant de procéder au déploiement, notamment Active Directory, DNS, certs et Fileshares.'
ms.openlocfilehash: 00b7828cfc06dd9d0ea1d7097580c9c25317e95a
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790286"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Configuration environnementale requise pour Skype entreprise Server 2015
 
**Résumé :** Configurez votre configuration non-serveur requise pour Skype entreprise Server 2015. Vous souhaiterez peut-être configurer un grand nombre d’éléments avant de procéder au déploiement, notamment Active Directory, DNS, certs et Fileshares.
  
Qu’est-ce que la configuration environnementale requise pour Skype entreprise Server 2015 ? En fait, nous avons mis tous les éléments qui ne sont pas directement liés à ce sujet, donc vous n’avez pas à faire autant de clics. Si vous recherchez les conditions préalables du serveur, vous pouvez consulter la [Configuration requise pour le serveur pour Skype entreprise server 2015](server-requirements.md) . la planification de la [mise en réseau](../../plan-your-deployment/network-requirements/network-requirements.md) est également documentée séparément. Dans le cas contraire, voici ce que nous avons trouvé dans cet article :
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Domain Name System)](environmental-requirements.md#DNS)
  
- [Certificats](environmental-requirements.md#Certs)
  
- [Partage de fichiers](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Bien que la quantité importante de données de configuration pour les serveurs et les services soit stockée dans le magasin central de gestion de Skype entreprise Server 2015, certaines choses sont toujours stockées dans Active Directory :
  
|**Objets Active Directory**|**Types d’objets**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions pour Lync Server 2013 et Lync Server 2010, pour assurer la compatibilité descendante avec les versions prises en charge précédentes.  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Objets contact pour les applications (comme l’application Response Group et l’application de surveillance de conférence).  <br/> |
||Données publiées pour la compatibilité descendante.  <br/> |
||Un point de contrôle de service (SCP) pour le magasin central de gestion.  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation des contrôleurs de domaine

Quel est le système d’exploitation du contrôleur de domaine qui peut être utilisé ? Nous disposons de la liste suivante :

- Windows Server 2019 (vous devez disposer de la mise à jour cumulative 5 de Skype entreprise Server 2015 ou version ultérieure)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
À présent, le niveau fonctionnel de tout domaine sur lequel vous déployez Skype entreprise Server 2015 et le niveau fonctionnel de forêt de n’importe quelle forêt dans laquelle vous déployez Skype entreprise Server 2015 doivent être l’un des suivants :

- Windows Server 2019 (vous devez disposer de la mise à jour cumulative 5 de Skype entreprise Server 2015 ou version ultérieure)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Est-il possible d’avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, tant qu’il y a également des contrôleurs de domaine accessibles en écriture disponibles sur le même site que le serveur Skype entreprise.
  
À présent, il est important de savoir que Skype entreprise Server 2015 ne prend pas en charge les domaines à étiquette unique. Qu’est-ce qu’elles ? Si vous avez un domaine racine nommé contoso. local, cela va être parfait. Si vous disposez d’un domaine racine qui vient d’être nommé local, cela ne fonctionne pas, et n’est pas pris en charge en conséquence. Pour plus d’informations [, consultez cet article de la base de connaissances](https://support.microsoft.com/kb/300684/en-us).
  
Skype entreprise Server 2015 ne prend pas non plus en charge le changement de nom des domaines. Si vous avez vraiment fait cela, vous devrez désinstaller Skype entreprise Server 2015, effectuer le changement de nom du domaine, puis réinstaller Skype entreprise Server 2015.
  
Enfin, vous pouvez être confronté à un domaine avec un environnement AD DS verrouillé, et c’est le droit. Nous avons plus d’informations sur la façon de déployer Skype entreprise Server 2015 dans ce type d’environnement dans les documents de déploiement.
  
### <a name="ad-topologies"></a>Topologies AD

Les topologies de Skype entreprise Server 2015 prises en charge sont les suivantes :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources avec Skype entreprise Online et Azure Active Directory Connect
    
Nous disposons de diagrammes et de descriptions pour vous aider à déterminer la topologie que vous avez dans votre environnement, ou ce que vous devrez peut-être configurer avant d’installer Skype entreprise Server 2015. Pour simplifier, nous incluons également une clé :
  
![Le est une clé pour les icônes utilisées pour les diagrammes de topologie Skype entreprise](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Diagramme d’une forêt Active Directory unique avec un seul domaine](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Il ne s’agit pas d’une seule et même forêt de domaines, il s’agit d’une topologie commune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Diagramme de forêt unique, d’arborescence unique et de domaines plusieurs](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme montre une seule forêt, encore une fois, mais elle comporte également un ou plusieurs domaines enfants (trois dans cet exemple). Par conséquent, le domaine dans lequel les utilisateurs sont créés peut être différent du domaine dans lequel Skype entreprise Server 2015 est déployé. Pourquoi vous en inquiéter ? N’oubliez pas que lorsque vous déployez un pool frontal Skype entreprise Server, tous les serveurs de ce pool doivent se trouver dans un seul domaine. Vous pouvez utiliser l’administration entre domaines via la prise en charge de Skype entreprise Server pour les groupes d’administrateurs universels Windows.
  
Retour au diagramme ci-dessus, vous pouvez voir que les utilisateurs d’un domaine peuvent accéder aux pools Skype entreprise Server à partir du même domaine ou de différents domaines, même si ces utilisateurs se trouvent dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Diagramme à une seule forêt, plusieurs arborescences et espaces de noms disjoints](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Il se peut que vous disposiez d’une topologie similaire à celle de ce diagramme, où vous avez une forêt, mais au sein de cette forêt, il s’agit de plusieurs domaines, avec des espaces de noms AD distincts. Si c’est le cas, ce diagramme est une excellente illustration, car nous avons des utilisateurs dans trois domaines différents accédant à Skype entreprise Server 2015. Les traits pleins indiquent qu’ils accèdent à un pool Skype entreprise Server dans leur propre domaine, tandis qu’une ligne en pointillés indique qu’ils accèdent à un pool dans une autre arborescence.
  
Comme vous pouvez le voir, les utilisateurs dans le même domaine, la même arborescence, ou même une arborescence différente peuvent accéder aux pools.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Plusieurs forêts dans un diagramme de topologie de forêt centrale](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype entreprise Server 2015 prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Si vous n’êtes pas certain de ce que vous avez, la forêt centrale de la topologie utilise des objets pour représenter les utilisateurs dans les autres forêts et héberge des comptes d’utilisateur pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? En fait, un produit de synchronisation d’annuaires (tel que Forefront Identity Manager ou FIM) gère les comptes d’utilisateur de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, cette modification est synchronisée avec le contact correspondant dans la forêt centrale.
  
En clair, si votre infrastructure AD est sur place, le déplacement vers cette topologie n’est peut-être pas facile, mais si vous y êtes déjà ou si vous planifiez encore votre infrastructure de forêt, il peut s’agir d’un bon choix. Vous pouvez centraliser votre déploiement de Skype entreprise Server 2015 au sein d’une seule forêt, tandis que les utilisateurs peuvent rechercher, communiquer et afficher la présence d’autres utilisateurs dans n’importe quelle forêt. Toutes les mises à jour de contacts de l’utilisateur sont gérées automatiquement avec le logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype entreprise
<a name="BKMK_multipleforestopology"> </a>

![Plusieurs forêts dans un diagramme de topologie de forêt de ressources](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt de ressources est également prise en charge ; Il s’agit d’une forêt dédiée à l’exécution de vos applications serveur, comme Microsoft Exchange Server et Skype entreprise Server 2015. Cette forêt de ressources héberge également une représentation synchronisée des objets utilisateur actifs, mais aucun compte d’utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident, et ils ont une relation d’approbation au niveau de la forêt avec la forêt de ressources.
  
Notez qu’Exchange Server peut être déployé dans la même forêt de ressources que Skype entreprise Server ou dans une autre forêt.
  
Pour déployer Skype entreprise Server 2015 dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs (si Microsoft Exchange Server est déjà dans l’environnement, cela peut être fait pour vous). Ensuite, vous aurez besoin d’un outil de synchronisation d’annuaires (comme Forefront Identity Manager ou FIM) pour gérer les comptes d’utilisateurs tout au long de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à la topologie décrite dans la rubrique [plusieurs forêts dans une topologie de forêt de ressources Skype entreprise](environmental-requirements.md#BKMK_multipleforestopology).
  
Dans cette topologie, il existe une ou plusieurs forêts d’utilisateurs, et Skype entreprise Server est déployé dans une forêt de ressources dédiée. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt, et configuré pour un environnement hybride avec Exchange Online, ou des services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources avec Skype entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Présente deux forêts Active Directory, une forêt utilisateur et une forêt de ressources. Les deux forêts ont une relation d’approbation. Elles sont synchronisées avec Microsoft 365 ou Office 365 à l’aide d’Azure AD Connect. Tous les utilisateurs sont activés pour Skype entreprise via Microsoft 365 ou Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il y a plusieurs forêts en local, avec une topologie de forêt de ressources. Il existe une relation de confiance totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser les comptes entre les forêts d’utilisateurs locales et Microsoft 365 ou Office 365.
  
 L’organisation dispose également de Microsoft 365 ou Office 365, et utilise [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) pour synchroniser ses comptes locaux avec Microsoft 365 ou Office 365. Les utilisateurs qui sont activés pour Skype entreprise sont activés via Microsoft 365 ou Office 365 et Skype entreprise online. Skype entreprise Server n’est pas déployé en local.
  
L’authentification unique est fournie par une batterie de serveurs AD FS (Active Directory Federation Services) située dans la forêt de l’utilisateur.
  
Dans ce scénario, il est pris en charge pour déployer Exchange sur site, Exchange Online, une solution Exchange hybride ou ne pas déployer Exchange. (Le diagramme affiche uniquement Exchange sur site, mais les autres solutions Exchange sont également entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources avec Skype entreprise hybride
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il existe une ou plusieurs forêts d’utilisateurs locales, et Skype entreprise est déployé dans une forêt de ressources dédiée et est configuré pour le mode hybride avec Skype entreprise online. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt, et peut être configuré pour une configuration hybride avec Exchange Online. Par ailleurs, les services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux.
  
Pour plus d’informations, consultez [la rubrique Configure a multi-Forest Environment for Hybrid Skype for Business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype entreprise Server 2015 requiert DNS, pour les raisons suivantes :
  
- Le DNS permet à Skype entreprise Server 2015 de découvrir les serveurs ou pools internes, ce qui permet des communications de serveur à serveur.
    
- DNS permet aux ordinateurs clients de découvrir le pool frontal ou le serveur Standard Edition qui est utilisé pour les transactions SIP.
    
- Il associe des URL simples aux conférences avec les serveurs hébergeant ces conférences.
    
- DNS permet aux utilisateurs et aux ordinateurs clients externes de se connecter à vos serveurs Edge, ou au proxy inverse HTTP, pour la messagerie instantanée ou les conférences.
    
- Elle permet aux appareils de communications unifiées qui ne sont pas connectés de découvrir le pool frontal ou le serveur Standard Edition qui exécute le service Web de mise à jour des périphériques pour obtenir les mises à jour et les journaux d’envoi.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services Web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres de leurs appareils.
    
- Et il est utilisé dans l’équilibrage de la charge DNS.
    
Il est important de noter que Skype entreprise Server 2015 ne prend pas en charge les noms de domaine internationaux (IDN).
  
Il est extrêmement important de se souvenir que tout nom de DNS est identique au nom de l’ordinateur configuré sur un serveur utilisé par Skype entreprise Server 2015. Plus précisément, nous ne pouvons pas avoir de noms courts dans l’environnement et vous devez avoir un nom de domaine complet pour le générateur de topologie.
  
Cela semble logique pour tout ordinateur déjà joint à un domaine, mais si vous avez un serveur Edge qui n’est pas joint à votre domaine, il peut avoir la valeur par défaut Short, sans suffixe de domaine. Assurez-vous que ce n’est pas le cas, dans DNS ou sur le serveur Edge, ou sur tout serveur ou pool Skype entreprise Server 2015.
  
Et ne sont pas autorisés à utiliser des caractères Unicode ou des traits de soulignement. Les caractères standard (qui sont A-Z, a-z, 0-9 et les tirets) sont ceux qui seront pris en charge par les autorités de certification publiques et DNS externes (vous devez affecter des noms de domaine complets au numéro de série dans le certificat, n’oubliez pas), vous pouvez ainsi vous faire un grand nombre de grief si vous avez un nom en tête.
  
Pour plus d’informations sur les exigences DNS pour la mise en réseau, consultez la section [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de notre documentation de planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des opérations les plus importantes que vous pouvez effectuer avant de procéder au déploiement est de vérifier que vos certificats sont dans l’ordre. Skype entreprise Server 2015 a besoin d’une infrastructure à clé publique (PKI) pour les connexions TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security). En gros, pour communiquer de manière standardisée de façon standardisée, Skype entreprise Server utilise des certificats émis par des autorités de certification (ca).
  
Voici quelques-unes des choses que Skype entreprise Server 2015 utilise les certificats pour :
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération à l’aide de la découverte automatique de partenaires via le DNS
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Communication avec les applications Web et Outlook Web Access (OWA)
    
La planification du certificat est donc obligatoire. À présent, examinons une liste de certaines choses que vous devez garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide d’un algorithme de signature pris en charge par le système d’exploitation. Skype entreprise Server 2015 prend en charge la suite SHA-1 et SHA-2 de tailles de condensé (224, 256, 384 et 512 bits) et satisfait ou dépasse la configuration requise du système d’exploitation.
    
- L’auto-enregistrement est pris en charge pour les serveurs internes exécutant Skype entreprise Server 2015.
    
- L’enregistrement automatique n’est pas pris en charge pour les serveurs Edge de Skype entreprise Server 2015.
    
- Pour soumettre une demande de certificat web à une Autorité de certification Windows Server 2003, vous devez utiliser un ordinateur exécutant Windows Server 2003 avec SP2 ou Windows XP.
    
> [!NOTE]
> Bien que KB922706 offre une prise en charge pour la résolution des problèmes liés à l’inscriptions de certificats Web par rapport à une authentification Web des services de certificats Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat à une autorité de certification Windows Server 2003. 
  
> [!NOTE]
> L’utilisation de l’algorithme de signature RSASSA-PSS n’est pas prise en charge et peut entraîner des erreurs de connexion et de transfert d’appel, entre autres problèmes. 

> [!NOTE]
> Skype entreprise Server 2015 ne prend pas en charge les certificats CNG.
  
- Les longueurs de clés de chiffrement de 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé de 2048 et supérieures sont recommandées.
    
- L’algorithme de chiffrement par défaut, ou signature de hachage, est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
Par conséquent, il existe un grand nombre de niveaux de confort grâce à la demande de certificats à une autorité de certification. Nous allons vous donner des conseils supplémentaires ci-dessous pour faciliter votre planification.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin de certificats pour la plupart de vos serveurs internes, et vous les obtiendrez très probablement à partir d’une autorité de certification interne (celle qui se trouve dans votre domaine). Si vous le souhaitez, vous pouvez demander ces certificats à une autorité de certification externe (située sur Internet). Si vous vous demandez à quelle autorité de certification publique vous devez vous rendre, vous pouvez consulter la liste des [partenaires de certificat de communications unifiées](/SkypeForBusiness/certification/services-ssl) .
  
Vous aurez également besoin de certificats lorsque Skype entreprise Server 2015 communique avec d’autres applications et serveurs, tels que Microsoft Exchange Server. Cela devra évidemment être un certificat que ces autres applications et serveurs peuvent utiliser de manière prise en charge. Skype entreprise Server 2015 et d’autres produits Microsoft prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Si cela vous intéresse, nous disposons d’un article de planification supplémentaire pour OAuth et Skype entreprise Server 2015.
  
Skype entreprise Server 2015 prend également en charge (sans exiger) des certificats signés à l’aide de la fonction de hachage cryptographique SHA-256. Pour prendre en charge l’accès externe à l’aide de l’algorithme SHA-256, le certificat externe doit être émis par une autorité de certification publique à l’aide de l’algorithme SHA-256.
  
Pour essayer et conserver des choses simples, nous avons placé les exigences de certificat pour les serveurs Standard Edition, les pools frontaux et d’autres rôles, dans les tableaux suivants, avec la contoso.com fictive utilisée pour des exemples (vous utiliserez probablement d’autres éléments pour votre environnement). Il s’agit de tous les certificats de serveur Web standard, avec des clés privées qui ne sont pas exportables. Voici quelques éléments supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) du serveur est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Chaque nom convivial de certificat doit être unique dans le magasin de l’ordinateur.
    
- Conformément aux exemples de noms ci-dessous, si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devez l’ajouter à l’autre nom de sujet du certificat (SAN).
    
Certificats pour les serveurs Standard Edition :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN = SE01. contoso. com ; SAN = SE01. contoso. com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur le serveur Standard Edition Server, le nom de domaine complet du serveur est le même que celui du pool.  <br/> L’Assistant détecte tous les domaines SIP que vous avez spécifiés lors de l’installation et les ajoute automatiquement en tant que autres noms du sujet.  <br/> Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web interne (identique au nom de domaine complet du serveur)  <br/> AND  <br/> • Répondre aux URL simples  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = \* . contoso.com  <br/> |Vous ne pouvez pas remplacer le nom de domaine complet Web interne dans le générateur de topologie.  <br/> Si vous avez plusieurs URL simples de réunion, vous devez les inclure toutes en tant que San.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web externe  <br/> AND  <br/> • URL simple d’accès à distance  <br/> • Répondre aux URL simples par domaine SIP  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \* . contoso.com  <br/> |Si vous avez plusieurs URL simples de réunion, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour les serveurs frontaux dans un pool frontal Enterprise Edition :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN = EEpool. contoso. com ; SAN = EEpool. contoso. com ; SAN = ee01. contoso. com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web interne (qui n’est pas le même que le nom de domaine complet du serveur)  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet du pool Skype entreprise  <br/> AND  <br/> • Répondre aux URL simples  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = \* . contoso.com  <br/> |Si vous avez plusieurs URL simples de réunion, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web externe  <br/> AND  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \* . contoso.com  <br/> |Si vous avez plusieurs URL simples de réunion, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool directeur  <br/> |Nom de domaine complet (FQDN) du directeur, nom de domaine complet du pool directeur.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous aurez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP dont vous disposez).  <br/> |pool.contoso.com ; SAN = DIR01. contoso. com  <br/> Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web interne (identique au nom de domaine complet du serveur)  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet du pool Skype entreprise  <br/> AND  <br/> • Répondre aux URL simples  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = DIR01. contoso. com ; SAN = DIR01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN = \* . contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web externe  <br/> AND  <br/> • Répondre aux URL simples par domaine SIP  <br/> • URL simple d’accès à distance  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |Le nom de domaine complet du directeur de site Web externe doit être différent du pool frontal ou du serveur frontal.  <br/> SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = \* . contoso.com  <br/> |
   
Certificats pour le serveur de médiation autonome :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN = medsvr01. contoso. net  <br/> |
   
Certificats pour Survivable Branch Appliance :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appliance  <br/> |SIP.\<sipdomain\> (vous n’avez besoin que d’une seule entrée par domaine SIP)  <br/> |SN = sba01. contoso. net ; SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificats pour votre serveur de conversation permanente

Lors de l’installation de votre serveur de conversation permanente, vous aurez besoin d’un certificat émis par la même autorité de certification que celle utilisée par vos serveurs internes Skype entreprise Server 2015. Cette opération doit être exécutée pour chaque serveur exécutant les services Web de conversation permanente pour le téléchargement/téléchargement de fichiers. Nous vous recommandons vivement de disposer des certificats requis avant de commencer l’installation de la conversation permanente et, si votre autorité de certification est externe, encore plus (ces éléments peuvent prendre un peu de temps pour être émis).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype entreprise Server 2015 prend en charge l’utilisation d’un **certificat public unique** pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification a/V, tous assurés via le (s) serveur (s) Edge. Votre interface interne Edge utilisera généralement un certificat privé émis par votre autorité de certification interne, mais si vous le souhaitez, vous pouvez également utiliser un certificat public pour cela, si elle provient d’une autorité de certification approuvée.
  
Votre proxy inverse (RP) doit également utiliser un certificat public et chiffre la communication de votre RP vers les clients et le RP vers les serveurs internes à l’aide du protocole HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez la mobilité et que vous prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines autres entrées de nom de sujet supplémentaires sur vos certificats afin de prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Quels certificats ? Vous aurez besoin de noms SAN pour la découverte automatique sur les certificats ici :
  
- pool directeur
    
- pool frontal
    
- Proxy inverse
    
Nous allons répertorier les détails dans chaque tableau ci-dessous.
  
À présent, il s’agit là d’un peu de planification possible, mais parfois vous avez déployé Skype entreprise Server 2015 sans avoir à déployer la mobilité, et cela se produit lorsque vous avez déjà des certificats dans votre environnement. Leur réémission via une autorité de certification interne est relativement facile, mais avec des certificats publics provenant d’une autorité de certification publique, qui peuvent être un peu plus onéreux.
  
Si c’est ce que vous regardez, et si vous avez un grand nombre de domaines SIP (ce qui rend l’ajout de réseaux SAN plus onéreux), vous pouvez configurer votre proxy inverse de sorte qu’il utilise le protocole HTTP pour la demande de service de découverte automatique initiale, au lieu d’utiliser le protocole HTTPs (configuration par défaut). La rubrique Planning for Mobility contient plus d’informations à ce sujet.
  
Conditions requises pour les certificats de pool directeur et de pool frontal :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN = lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover.\<sipdomain\>  <br/> |
   
Vous pouvez également utiliser SAN = \* .\<sipdomain\>
  
Conditions requises pour le certificat de proxy inverse (autorité de certification publique) :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover.\<sipdomain\>  <br/> |
   
Ce SAN doit être affecté au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> Votre écouteur de proxy inverse va avoir des réseaux SAN pour vos URL de services Web externes. Voici quelques exemples : SAN = skypewebextpool01. contoso. com et dirwebexternal.contoso.com, si vous avez déployé le directeur (ce qui est facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype entreprise Server 2015 peut utiliser le même partage de fichiers pour tout le stockage de fichiers. Vous devez garder les points suivants à l’esprit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (direct Attached Storage) ou un réseau SAN (Storage Area Network), ainsi que sur un système de fichiers distribués (DFS) ainsi qu’un système RAID (Redundant Array of Independent Disks) pour les magasins de fichiers. Pour en savoir plus sur DFS pour Windows Server 2012, consultez [cette page DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Nous vous recommandons d’utiliser un cluster partagé pour le partage de fichiers. Si vous utilisez un, vous devez clusteriser Windows Server 2012 ou Windows Server 2012 R2. Windows Server 2008 R2 est également acceptable. Pourquoi les dernières fenêtres ? Il est possible que les versions antérieures ne disposent pas des autorisations appropriées pour activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de cluster pour créer les partages de fichiers, et cette [procédure de création de partages de fichiers dans un](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) article de cluster vous aidera à obtenir ces détails.
    
> [!CAUTION] 
> Il est important de comprendre que l’utilisation du stockage rattaché au réseau (NAS) comme partage de fichiers n’est pas prise en charge ; vous pouvez donc utiliser l’une des options indiquées ci-dessus. 
  
