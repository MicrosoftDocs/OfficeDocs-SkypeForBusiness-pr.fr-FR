---
title: Conditions préalables d’environnement pour Skype Entreprise Server 2015
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
description: 'Résumé : configurez votre configuration non serveur requise pour Skype entreprise Server 2015. Vous pouvez configurer plusieurs éléments avant de procéder à votre déploiement, notamment Active Directory, DNS, certs et Fileshares.'
ms.openlocfilehash: 7af4587dfef237a6449dbfa9a271910398ec8a41
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801904"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**Résumé :** Configurez votre configuration non serveur requise pour Skype entreprise Server 2015. Vous pouvez configurer plusieurs éléments avant de procéder à votre déploiement, notamment Active Directory, DNS, certs et Fileshares.
  
Quelle est la configuration environnementale requise pour Skype entreprise Server 2015 ? Pour l’instant, nous avons placé tout ce qui n’est pas directement lié à ce sujet, et vous n’avez donc pas besoin de cliquer sur le bouton. Si vous recherchez des conditions préalables pour le serveur, vous pouvez consulter la [Configuration requise pour le serveur pour Skype entreprise Server 2015](server-requirements.md) document[documentation.](../../plan-your-deployment/network-requirements/network-requirements.md) Sinon, voici ce que nous avons dans cet article :
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificats](environmental-requirements.md#Certs)
  
- [Partage de fichiers](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Même si de nombreuses données de configuration pour les serveurs et les services sont stockées dans Skype entreprise Server 2015, il existe certains éléments qui sont toujours stockés dans Active Directory :
  
|**Objets Active Directory**|**Types d’objets**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions pour Lync Server 2013 et Lync Server 2010, afin d’assurer la compatibilité descendante avec les versions prises en charge précédentes.  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Objets de contact pour applications (par exemple, l’application Response Group et l’application attendant).  <br/> |
||Données publiées pour la compatibilité descendante  <br/> |
||Un point de contrôle de service (SCP) pour le centre de gestion central.  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation pour les contrôleurs de domaine

Quel système d’exploitation de contrôleur de domaine faut-il alors utiliser ? Nous avons la liste suivante :

- Windows Server 2019 (vous devez disposer de Skype entreprise Server 2015 cumulative Update 5 ou version ultérieure)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
À présent, le niveau de fonctionnalité du domaine de tout domaine sur lequel vous déployez Skype entreprise Server 2015 et le niveau fonctionnel de la forêt de n’importe quelle forêt de déploiement de Skype entreprise Server 2015 doivent être l’un des suivants :

- Windows Server 2019 (vous devez disposer de Skype entreprise Server 2015 cumulative Update 5 ou version ultérieure)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Pouvez-vous avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, dans la mesure où un contrôleur de domaine accessible en écriture est disponible.
  
À présent, il est important de savoir que Skype entreprise Server 2015 ne prend pas en charge les domaines à mention unique. Que sont-ils ? Si vous avez un domaine racine appelé contoso. local, cela va être bien. Si vous avez un domaine racine appelé simplement local, il n’y a pas de fonctionnement et il n’est pas pris en charge en conséquence. Ce article de la [base de connaissances](https://support.microsoft.com/kb/300684/en-us)contient quelques informations supplémentaires.
  
Skype entreprise Server 2015 ne supporte pas non plus le changement de nom de domaines. Si c’est le cas, vous devez désinstaller Skype entreprise Server 2015, effectuer le changement de nom de domaine, puis réinstaller Skype entreprise Server 2015.
  
Enfin, vous avez peut-être affaire à un domaine avec un environnement de services d’annuaire Active Directory (AD DS) verrouillé et c’est tout juste. Nous avons plus d’informations sur le déploiement de Skype entreprise Server 2015 dans ce type d’environnement dans les documents de déploiement.
  
### <a name="ad-topologies"></a>Topologies AD

Les topologies prises en charge par Skype entreprise Server 2015 sont les suivantes :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
    
Nous avons des diagrammes et des descriptions qui vous aideront à déterminer quelle topologie vous avez dans votre environnement ou ce que vous devrez configurer avant d’installer Skype entreprise Server 2015. Pour le simplifier, nous avons également une touche :
  
![Il s’agit d’une clé pour les icônes utilisées pour les schémas de topologie Skype Entreprise.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Schéma d’une forêt Active Directory unique avec un seul domaine](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Il s’agit d’une seule et même forêt de domaine ; c’est une topologie courante.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Schéma d’une forêt unique avec un arbre unique et plusieurs domaines](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme illustre de nouveau une forêt unique, mais elle a un ou plusieurs domaines enfants aussi (il en existe trois dans cet exemple spécifique). Le domaine dans lequel les utilisateurs sont créés peut être différent de celui sur lequel Skype entreprise Server 2015 est déployé. Est-ce problématique ? Il est important de garder à l’esprit que lorsque vous déployez une grappe frontale Skype entreprise Server, tous les serveurs de ce pool doivent faire partie d’un domaine unique. Vous pouvez bénéficier d’une administration entre domaines grâce à la prise en charge de Skype entreprise Server par le biais de groupes d’administrateurs Windows universels.
  
Dans le diagramme ci-dessus, vous pouvez voir que les utilisateurs d’un domaine peuvent accéder aux pools de serveurs Skype entreprise du même domaine ou à partir de différents domaines, même s’ils se trouvent dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Schéma d’une forêt unique avec des arbres multiples et des espaces de noms disjoints](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Il est possible que vous disposiez d’une topologie similaire à celle-ci, dans laquelle vous disposez d’une seule forêt, mais au sein de cette forêt, il existe plusieurs domaines, avec des espaces de noms distincts. Si tel est le cas, il s’agit d’une bonne illustration, dans la mesure où les utilisateurs utilisent trois domaines différents pour accéder à Skype entreprise Server 2015. Les lignes pleines indiquent qu’elles permettent d’accéder à un pool de serveurs Skype entreprise dans leur propre domaine, tandis qu’un trait en pointillé indique qu’il y a un groupe dans une même arborescence.
  
Comme vous pouvez le voir, les utilisateurs dans le même domaine, la même arborescence ou même dans une arborescence différente sont en mesure d’accéder aux pools avec succès.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Schéma de forêts multiples dans une topologie de forêts centralisée](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype entreprise Server 2015 prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Si vous n’êtes pas sûr de ce que vous avez, la forêt centrale dans la topologie utilise des objets pour représenter les utilisateurs dans les autres forêts et héberge les comptes d’utilisateurs pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? Par exemple, un produit de synchronisation d’annuaires (tel que Forefront Identity Manager ou FIM) gère les comptes d’utilisateurs de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, ce changement est synchronisé avec le contact correspondant dans la forêt centrale.
  
Pour l’instant, si votre infrastructure publicitaire est inaltérable, il est possible que vous ne soyez pas facile à faire, mais si vous en soyez déjà là ou que vous soyez en mesure de planifier votre infrastructure de forêt, c’est un bon choix. Vous pouvez centraliser votre déploiement de Skype entreprise Server 2015 au sein d’une même forêt, même si les utilisateurs peuvent rechercher, communiquer et afficher la présence d’autres utilisateurs de n’importe quelle forêt. Toutes les mises à jour des contacts utilisateur sont gérées automatiquement à l’aide du logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise
<a name="BKMK_multipleforestopology"> </a>

![Forêts multiples dans un schéma de topologie de forêts de ressources](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt de ressources est également prise en charge. C’est là où une forêt est dédiée à l’exécution de vos applications serveur, comme Microsoft Exchange Server et Skype entreprise Server 2015. Cette forêt de ressources héberge également une représentation synchronisée des objets d’utilisateurs actifs, mais aucun compte utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident et ceux-ci ont une relation de confiance au niveau de la forêt avec la forêt de ressources.
  
Notez qu’Exchange Server peut être déployé dans la même forêt de ressources que Skype entreprise Server ou dans une autre forêt.
  
Pour déployer Skype entreprise Server 2015 dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts des utilisateurs (si Microsoft Exchange Server est déjà dans l’environnement, cela peut être fait pour vous). Ensuite, vous avez besoin d’un outil de synchronisation d’annuaires (par exemple, Forefront Identity Manager ou FIM) pour gérer les comptes d’utilisateur par le biais de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à celle décrite dans la rubrique [Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online](environmental-requirements.md#BKMK_multipleforestopology).
  
Dans cette topologie, il existe une ou plusieurs forêts utilisateur et Skype entreprise Server est déployé dans une forêt de ressources dédiée. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt et configuré pour une connexion hybride avec Exchange Online, ou les services de messagerie peuvent être fournis uniquement par Exchange Online pour les comptes locaux. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Représente deux forêts AD : une forêt d’utilisateurs et une forêt de ressources. Les deux forêts sont liées par une relation de confiance. Elles sont synchronisées avec Office 365 via Azure AD Connect. Tous les utilisateurs peuvent accéder à Skype Entreprise via Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il existe plusieurs forêts sur site avec une topologie de forêt de ressources. Il existe une relation d’approbation totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser des comptes entre les forêts d’utilisateurs sur site et Office 365.
  
 L’organisation dispose également d’Office 365 et utilise [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) pour synchroniser leurs comptes locaux avec Office 365. Les utilisateurs activés pour Skype entreprise sont activés par le biais d’Office 365 et de Skype entreprise online. Skype entreprise Server n’est pas déployé en local.
  
L’authentification unique est fournie par une batterie de serveurs Active Directory Federation Services située dans la forêt utilisateur.
  
Dans ce scénario, il est pris en charge pour le déploiement d’Exchange en local, d’Exchange Online, d’une solution Exchange hybride ou d’un déploiement Exchange. (Le schéma présente uniquement Exchange en local, mais les autres solutions Exchange sont entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources et un déploiement hybride de Skype Entreprise 
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il existe un ou plusieurs forêts utilisateurs locales et Skype entreprise est déployé dans une forêt de ressources dédiées et est configuré pour le mode hybride dans Skype entreprise online. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt et peut être configuré pour une connexion hybride avec Exchange Online. Vous pouvez également fournir des services de messagerie exclusivement via Exchange Online pour les comptes locaux.
  
Pour plus d’informations, reportez-vous à [la rubrique Configuration d’un environnement de forêts multiples pour Skype entreprise hybride](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Pour les raisons suivantes, Skype entreprise Server 2015 nécessite le système DNS :
  
- Ce service permet aux utilisateurs de Skype entreprise Server 2015 de découvrir les serveurs internes ou les pools, ce qui permet des communications serveur à serveur.
    
- DNS permet aux ordinateurs clients de découvrir le pool frontal ou le serveur Standard Edition utilisé pour les transactions SIP.
    
- Il associe des URL simples pour des conférences avec les serveurs hébergeant ces conférences.
    
- Le système DNS permet aux utilisateurs externes et aux ordinateurs clients de se connecter à vos serveurs Edge ou au proxy HTTP inversement pour la messagerie instantanée ou les conférences.
    
- Il permet aux appareils de communications unifiées (UC) qui ne sont pas connectés dans la découverte du pool frontal ou d’un serveur Standard Edition qui exécute le service Web de mise à jour des périphériques pour obtenir des mises à jour et envoyer des journaux.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.
    
- De plus, DNS utilise l’équilibrage de charges.
    
Il est important de noter que Skype entreprise Server 2015 ne prend pas en charge les noms de domaines internationaux (IDNs).
  
Il est très important de noter que le nom de l’ordinateur que vous utilisez est identique à celui configuré sur n’importe quel serveur utilisé par Skype entreprise Server 2015. Plus précisément, nous ne pouvons pas avoir de noms courts dans l’environnement, et doivent avoir des noms de domaine complets pour le générateur de topologie.
  
Cela semble logique pour tout ordinateur déjà joint à un domaine, mais si vous avez un serveur Edge qui n’est pas joint à votre domaine, il est possible qu’il ait un nom court par défaut, sans suffixe de domaine. Pour cela, assurez-vous que ce n’est pas le cas, que ce soit dans DNS ou sur le serveur Edge, ou sur un serveur ou un pool Skype entreprise Server 2015.
  
Et n’utilisez pas les caractères ou les traits de soulignement. Les caractères standard (qui sont A-Z, a-z, 0-9 et les traits d’Union) sont ceux que vous allez prendre en charge par les autorités de certification DNS et publique externes (vous devez attribuer des noms de domaine complets à la référence du certificat, n’oubliez pas), ce qui vous permettra de gagner beaucoup de grief si Nommez ce qui suit à l’esprit.
  
Pour en savoir plus sur les exigences du DNS pour le réseau, consultez la section [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de notre documentation consacrée à la planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des tâches les plus importantes à effectuer avant le déploiement est de vérifier que les certificats sont en ordre. Skype entreprise Server 2015 a besoin d’une infrastructure à clé publique (PKI) pour les connexions TLS (Transport Layer Security) et Mutual Transport Layer Security (MTLS). Fondamentalement, pour communiquer de manière sécurisée, Skype entreprise Server utilise des certificats émis par les autorités de certification (ca).
  
Voici quelques-unes des raisons pour lesquelles Skype entreprise Server 2015 utilise des certificats pour :
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération utilisant la découverte automatique de partenaires via le DNS
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Discuter avec des applications Web et Outlook Web Access (OWA)
    
C’est pourquoi le planning de certification a obligatoire. Examinons maintenant la liste de quelques éléments à garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Skype entreprise Server 2015 prend en charge la suite SHA-1 et SHA-2 de tailles synthétiques (224, 256, 384 et 512) et respecte ou dépasse la configuration requise du système d’exploitation.
    
- L’inscription automatique est prise en charge pour les serveurs internes exécutant Skype entreprise Server 2015.
    
- L’enregistrement automatique n’est pas pris en charge par les serveurs Edge Skype entreprise Server 2015.
    
- Lorsque vous envoyez une demande de certification basée sur le Web à une autorité de certification Windows Server 2003, vous devez la transmettre à partir d’un ordinateur exécutant Windows Server 2003 SP2 ou Windows XP.
    
> [!NOTE]
> Bien que l’article de la Base de connaissances Microsoft KB922706 indique comment résoudre les problèmes relatifs à l’inscription de certificats web lors d’une inscription auprès des services de certificat Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat auprès d’une autorité de certification Windows Server 2003. 
  
> [!NOTE]
> L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels.  

> [!NOTE]
> Skype entreprise Server 2015 ne prend pas en charge les certificats CNG.
  
- Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.
    
- L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
C’est pourquoi, et il existe un grand nombre de niveaux de confort grâce à la demande de certificats auprès d’une autorité de certification. Nous vous offrons quelques conseils supplémentaires ci-dessous pour rendre votre planification aussi simple que possible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin de certificats pour la plupart de vos serveurs internes, et il est probable que vous les obteniez auprès d’une autorité de certification interne (qui se trouve dans votre domaine). Le cas échéant, vous pouvez demander ces certificats à une autorité de certification externe (située sur Internet). Si vous vous demandez ce que vous devez faire, vous pouvez consulter la liste des [partenaires de certification de communications unifiées](/SkypeForBusiness/certification/services-ssl) .
  
Vous aurez également besoin de certificats lorsque Skype entreprise Server 2015 communiquera avec d’autres applications et serveurs, comme Microsoft Exchange Server. Ce certificat doit bien entendu être un certificat que ces autres applications et serveurs peuvent utiliser en mode de prise en charge. Skype entreprise Server 2015 et d’autres produits Microsoft prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Si cela vous intéresse, nous avons un article de planification supplémentaire pour les appels OAuth et Skype entreprise Server 2015.
  
Skype entreprise Server 2015 inclut également la prise en charge des certificats (sans nécessiter) signés à l’aide de la fonction de hachage de chiffrement SHA-256. Pour favoriser l’accès externe à l’aide de SHA-256, le certificat externe doit être émis par une autorité de certification publique utilisant SHA-256.
  
Pour vous permettre d’essayer et de simplifier les choses, nous avons mis en place la configuration requise pour les certificats pour les serveurs Standard Edition, les listes frontales et d’autres rôles, dans les tableaux ci-dessous, l’utilisation de contoso.com pour votre environnement). Il s’agit de tous les certificats de serveur web standard, avec des clés privées qui ne sont pas exportables. Quelques points supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Le nom convivial de chaque certificat doit être unique dans le magasin de l’ordinateur.
    
- Comme pour les exemples de noms ci-dessous, si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, ils doivent être ajoutés au nom de l’objet du certificat.
    
Certificats pour les serveurs Standard Edition :
  
|**Certificat**|**Nom du sujet/Nom courant**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur les serveurs Standard Edition Server Standard Edition Server, le nom de domaine complet du serveur est identique au nom de domaine complet du pool.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web interne (qui est identique au nom de domaine complet du serveur).  <br/> ET  <br/> • Respecter des URL simples  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN =\*. contoso.com  <br/> |Vous ne pouvez pas remplacer le FQDN Web interne dans le générateur de topologie.  <br/> Si vous disposez de plusieurs URL simples de réunion, vous devez les inclure toutes en tant qu’autres noms du sujet (SAN).  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web externes  <br/> ET  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • Respecter les URL simples par domaine SIP  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour serveurs frontaux dans une liste frontale :
  
|**Certificat**|**Nom du sujet/Nom courant**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet (FQDN) Web interne (différent du nom de domaine complet du serveur)  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet (FQDN) du pool Skype entreprise  <br/> ET  <br/> • Respecter des URL simples  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web externes  <br/> ET  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom du sujet/Nom courant**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool de directeurs  <br/> |Nom de domaine complet (FQDN) du réalisateur du pool de réalisateurs.  <br/> S’il s’agit du serveur d’ouverture de session automatique pour les clients et de la correspondance DNS stricte requise dans la stratégie de groupe, vous aurez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP que vous utilisez).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Si ce pool de directeurs est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous devez également disposer de SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web interne (qui est identique au nom de domaine complet du serveur).  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet (FQDN) du pool Skype entreprise  <br/> ET  <br/> • Respecter des URL simples  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web externes  <br/> ET  <br/> • Respecter les URL simples par domaine SIP  <br/> • URL d’accès à la Conférence rendez-vous  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |Le FQDN Web de Director doit être différent du serveur frontal ou du pool frontal.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificats pour un serveur de médiation autonome :
  
|**Certificat**|**Nom du sujet/Nom courant**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificats pour l’appareil de branchement Survivable :
  
|**Certificat**|**Nom du sujet/Nom courant**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appareil  <br/> |SIP. \<sipdomain\> (vous n’avez besoin que d’une seule entrée par domaine SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificats pour votre serveur de conversation permanente

Lors de l’installation de votre serveur de chat permanent, vous aurez besoin d’un certificat émis par la même autorité de certification que celle utilisée par vos serveurs internes Skype entreprise Server 2015. Cette opération est nécessaire pour chaque serveur exécutant les services Web chat permanent pour le téléchargement/téléchargement de fichiers. Nous vous conseillons vivement d’avoir le ou les certificats requis avant de commencer l’installation de chat permanent, et si votre autorité de certification est externe, il y a un peu plus de temps à s’exécuter.
  
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype entreprise Server 2015 prend en charge l’utilisation d’un **certificat public unique** pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification a/V, qui est fourni par le biais du ou des serveurs de bord. Votre interface interne Edge utilise généralement un certificat privé émis par votre autorité de certification interne, mais si vous le souhaitez, vous pouvez également utiliser un certificat public pour cela, s’il provient d’une autorité de certification approuvée.
  
Votre proxy inverse (RP) utilise également un certificat public et chiffre la communication de votre RP aux clients et du RP aux serveurs internes via HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez une mobilité et que vous prenez en charge la découverte automatique pour les clients mobiles, vous aurez besoin d’ajouter d’autres inscriptions de nom de sujet sur vos certificats pour prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Quels certificats ? Vous aurez besoin de noms SAN pour la découverte automatique sur les certificats ici :
  
- pool de directeurs
    
- pool de serveurs frontaux
    
- Proxy inverse
    
Les spécificités sont répertoriées dans chaque tableau ci-dessous.
  
C’est là qu’il s’agit d’une préversion correcte, mais parfois, vous avez déployé Skype entreprise Server 2015 sans vous soucier du déploiement de la mobilité et celle-ci apparaît sur la ligne lorsque vous disposez déjà d’un certificat dans votre environnement. La réémission de ces dernières par le biais d’une autorité de certification interne est généralement relativement simple, mais avec les certificats publics d’une autorité de certification publique qui peuvent être un peu plus pricy.
  
Si ce n’est pas le cas, et si vous disposez d’un grand nombre de domaines SIP (ce qui permet d’ajouter des réseaux SANS frais supplémentaires), vous pouvez configurer votre proxy inverse de façon à ce que la demande de service de découverte automatique initiale s’utilise au lieu d’utiliser HTTPs (par défaut). Configuration). La rubrique de planification de la mobilité contient plus d’informations à ce sujet.
  
Conditions requises pour les certificats du pool de réalisateur et du pool frontal :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Vous pouvez également utiliser le SAN\*. \<sipdomain\>
  
Exigences relatives au certificat de proxy inverse (autorité de certification publique)
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Ce SAN doit être attribué au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> L’écouteur de proxy inverse va disposer de réseaux SAN pour vos URL de services Web externes. Par exemple, il peut s’agir de SAN = skypewebextpool01. contoso. com et dirwebexternal.contoso.com, si vous avez déployé le directeur (facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype entreprise Server 2015 est en mesure d’utiliser le même partage de fichiers pour l’ensemble du stockage de fichiers. Gardez à l’esprit ce qui suit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), dont un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. Pour plus d’informations sur le système de fichiers DFS pour Windows Server 2012, consultez [cette page DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Nous vous recommandons d’utiliser un cluster partagé pour le partage de fichiers. Si vous utilisez un, vous devez disposer d’un cluster Windows Server 2012 ou Windows Server 2012 R2. Windows Server 2008 R2 est également acceptable. Pourquoi vous avez la dernière version de Windows ? Les versions plus anciennes ne disposent pas des autorisations appropriées pour activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de cluster pour créer les partages de fichiers, et cette [procédure de création de partages de fichiers sur un](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) article de cluster vous aidera à les résoudre.
    
> [!CAUTION] 
> Vous devez savoir que le dispositif de stockage réseau (NAS) ne prend pas en charge le partage de fichiers. Vous devez donc utiliser l’une des options proposées ci-après. 
  

