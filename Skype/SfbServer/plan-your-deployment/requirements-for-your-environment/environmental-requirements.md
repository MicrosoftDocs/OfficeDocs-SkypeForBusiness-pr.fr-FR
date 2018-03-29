---
title: Conditions préalables d’environnement pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Résumé : Configurer votre serveur non configuration requise pour Skype pour Business Server 2015. Il y a plusieurs choses que vous voudrez configuré avant d’effectuer votre déploiement, y compris Active Directory, DNS, certificats et partages.'
ms.openlocfilehash: 0d71140678654442caef112f6132695c76d3ea6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Conditions préalables d’environnement pour Skype Entreprise Server 2015
 
**Résumé :** Configurez votre serveur non configuration requise pour Skype pour Business Server 2015. Il y a plusieurs choses que vous voudrez configuré avant d’effectuer votre déploiement, y compris Active Directory, DNS, certificats et partages.
  
Ce qu’est une exigence de l’environnement pour Skype pour Business Server 2015 ? Eh bien, nous avons créé tout ce qui n’est pas directement liées dans cette rubrique, afin que vous n’avez pas à faire comme beaucoup en cliquant sur autour. Si vous recherchez des conditions préalables du serveur, vous pouvez extraire le document de [configuration serveur requise pour Skype pour Business Server 2015](server-requirements.md) la[Planification de la mise en réseau](../../plan-your-deployment/network-requirements/network-requirements.md) est également documenté séparément. Sinon, c’est ce que nous avons dans cet article :
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificats](environmental-requirements.md#Certs)
  
- [Partage de fichiers](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Tandis que de nombreuses données de configuration pour les serveurs et services est stocké dans Skype pour le magasin Central de gestion de 2015 Business Server, il existe certaines choses restent stockées dans Active Directory :
  
|**Objets Active Directory**|**Types d’objet**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions de Lync Server 2013 et Lync Server 2010 assurer la compatibilité descendante avec les précédentes versions prises en charge.  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Objets de contact pour les applications (comme l’application de groupe de réponse et l’application de la surveillance du conférence).  <br/> |
||Données publiées pour la compatibilité descendante  <br/> |
||Un service point de contrôle (SCP) pour le magasin Central de gestion.  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation pour les contrôleurs de domaine

Quel système d’exploitation de contrôleur de domaine faut-il alors utiliser ? Nous avons la liste suivante :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Maintenant, le niveau fonctionnel de domaine de n’importe quel domaine dans que vous déployez Skype pour 2015 de serveur d’entreprise et le niveau fonctionnel de la forêt d’une forêt que vous déployez Skype pour 2015 de serveur d’entreprise, doivent être une des opérations suivantes :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Pouvez-vous avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, dans la mesure où un contrôleur de domaine accessible en écriture est disponible.
  
Maintenant, il est important de savoir que Skype pour Business Server 2015 ne prend en charge une seule partie de domaines. Que sont-ils ? Si vous avez un domaine racine intitulé contoso.local, qui va bien. Si vous avez un domaine racine nommé simplement local, qui ne va pas fonctionner, et il n’est pas supportée par conséquent. Un peu plus à ce sujet a été écrit [dans cet article de la Base de connaissances](https://support.microsoft.com/kb/300684/en-us).
  
Skype pour Business Server 2015 également ne prend en charge les domaines du changement de nom. Si vous avez vraiment de le faire, puis vous allez doivent désinstaller Skype pour 2015 de serveur d’entreprise, effectuez le changement de nom de domaine et puis réinstallez Skype pour Business Server 2015.
  
Enfin, vous pouvez être confronté à un domaine avec un environnement de domaine Active Directory verrouillé, et c’est bon. Nous avons plus d’informations sur le déploiement de Skype pour Business Server 2015 dans ce type d’environnement dans les documents de déploiement.
  
### <a name="ad-topologies"></a>Topologies AD

Skype pour les topologies prises en charge de 2015 Business Server sont les suivantes :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
    
Nous avons les diagrammes et les descriptions pour aider à déterminer quelle topologie que vous avez dans votre environnement, ou vous devrez peut-être configurer avant d’installer Business Server 2015 Skype. Pour faire simple, nous incluons une clé :
  
![Il s’agit d’une clé pour les icônes utilisées pour les schémas de topologie Skype Entreprise.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Schéma d’une forêt Active Directory unique avec un seul domaine](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Vous ne trouverez pas plus simple, il s’agit d’une forêt à domaine unique, il s’agit d’une topologie commune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Schéma d’une forêt unique avec un arbre unique et plusieurs domaines](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme illustre de nouveau une forêt unique, mais elle a un ou plusieurs domaines enfants aussi (il en existe trois dans cet exemple spécifique). Les utilisateurs sont créés dans le domaine de peut être différent du domaine Skype pour Business Server 2015 est déployé sur. Est-ce problématique ? Il est important de se rappeler que lorsque vous déployez un Skype pour le pool d’entreprise serveur frontal, tous les serveurs de ce pool doivent être dans un domaine unique. Vous pouvez avoir administration interdomaine via Skype pour la prise en charge du serveur d’entreprise des groupes universels administrateur de Windows.
  
Sur le diagramme ci-dessus, vous pouvez voir que les utilisateurs d’un domaine peuvent accéder à Skype pour les pools de Business Server à partir du même domaine ou de domaines différents, même si ces utilisateurs sont dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Schéma d’une forêt unique avec des arbres multiples et des espaces de noms disjoints](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Il peut s’avérer que vous avez sélectionné une topologie similaire à ce schéma, dans lequel vous avez une forêt, mais dans cette forêt sont plusieurs domaines, avec des espaces de noms Active Directory séparé. Si qui s’est du cas, ce diagramme d’une bonne illustration, que nous avons des utilisateurs dans trois domaines différents accès à Skype pour Business Server 2015. Les traits pleins indiquent qu’ils accédez à un Skype pour le pool de serveur d’entreprise dans leur propre domaine, tandis qu’une ligne en pointillés indique elles vont complètement à un regroupement dans une autre arborescence.
  
Comme vous pouvez le voir, les utilisateurs dans le même domaine, la même arborescence ou même dans une arborescence différente sont en mesure d’accéder aux pools avec succès.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Schéma de forêts multiples dans une topologie de forêts centralisée](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype pour Business Server 2015 ne prend pas en charge plusieurs forêts configurées dans une topologie à forêt centrale. Si vous ne savez pas qui est ce dont vous disposez, la topologie de la forêt centrale utilise des objets qu’il contient pour représenter les utilisateurs dans les autres forêts et les comptes d’utilisateur hôtes pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? Ainsi, un produit de synchronisation d’annuaire (comme Forefront Identity Manager, ou FIM) gère les comptes d’utilisateurs de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, ce changement est synchronisé avec le contact correspondant dans la forêt centrale.
  
En clair, si votre infrastructure Active Directory est en place déplacement vers cette topologie peut-être pas facile, mais si vous êtes déjà là, ou encore planification votre infrastructure de forêt, ce peut être un bon choix. Vous pouvez centraliser votre Skype pour le déploiement de Business Server 2015 au sein d’une forêt unique, alors que les utilisateurs peuvent rechercher, communiquer et permet d’afficher la présence des autres utilisateurs dans une forêt. Toutes les mises à jour des contacts utilisateur sont gérées automatiquement à l’aide du logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise
<a name="BKMK_multipleforestopology"> </a>

![Forêts multiples dans un schéma de topologie de forêts de ressources](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt ressource est également pris en charge ; Il s’agit d’où une forêt est dédiée à l’exécution de vos applications serveur, telles que Microsoft Exchange Server et Skype pour Business Server 2015. Cette forêt de ressources héberge également une représentation synchronisée des objets d’utilisateurs actifs, mais aucun compte utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident et ceux-ci ont une relation de confiance au niveau de la forêt avec la forêt de ressources.
  
Notez qu’Exchange Server peuvent être déployé dans la même forêt de ressource que Skype pour Business Server ou dans une autre forêt.
  
Pour déployer Skype pour 2015 de serveur d’entreprise dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs (si Microsoft Exchange Server est déjà dans l’environnement, il peut être fait pour vous). Vous devrez alors un outil de synchronisation d’annuaire (comme Forefront Identity Manager, ou FIM) pour gérer les comptes d’utilisateur par le biais de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à celle décrite dans la rubrique [Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online](environmental-requirements.md#BKMK_multipleforestopology).
  
Dans cette topologie, il existe une ou plusieurs forêts d’utilisateurs et Skype pour Business Server est déployé dans une forêt de ressources dédiées. Exchange Server peut être déployé sur site dans la même forêt de ressource ou d’une autre forêt et configuré pour hybride avec Exchange Online, ou de services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Représente deux forêts AD : une forêt d’utilisateurs et une forêt de ressources. Les deux forêts sont liées par une relation de confiance. Elles sont synchronisées avec Office 365 via Azure AD Connect. Tous les utilisateurs peuvent accéder à Skype Entreprise via Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il existe plusieurs forêts sur site avec une topologie de forêt de ressources. Il existe une relation d’approbation totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser des comptes entre les forêts d’utilisateurs sur site et Office 365.
  
 L’organisation a Office 365 et utilise [Azure Active Directory se connecter](https://go.microsoft.com/fwlink/p/?LinkId=614836) pour synchroniser leurs comptes locaux avec Office 365. Les utilisateurs qui sont activés pour Skype pour entreprise sont activées via Office 365 et Skype pour entreprise en ligne. Skype pour Business Server n’est pas déployé sur site.
  
Ouverture de session d’authentification unique est fournie par une batterie de serveurs de Services de fédération Active Directory situé dans la forêt de l’utilisateur.
  
Dans ce scénario, il est pris en charge pour déployer Exchange sur site, Exchange Online, une solution Exchange hybride, ou de ne pas du tout de déploiement d’Exchange. (Le schéma présente uniquement Exchange en local, mais les autres solutions Exchange sont entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources et un déploiement hybride de Skype Entreprise 
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il y a une ou plusieurs locaux forêts d’utilisateurs et Skype pour entreprise est déployé dans une forêt de ressources dédiées et est configuré pour le mode hybride avec Skype pour l’activité en ligne. Exchange Server peut être déployé sur site dans la même forêt de ressource ou d’une autre forêt et peuvent être configuré pour hybride avec Exchange Online. Également, les services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux.
  
Pour plus d’informations, consultez [configurer un environnement à plusieurs forêts pour hybride Skype pour les entreprises](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype pour Business Server 2015 nécessite le système DNS, pour les raisons suivantes :
  
- Le système DNS permet de Skype pour 2015 de serveur Business découvrir les serveurs internes ou des pools, permettant ainsi les communications de serveur à serveur.
    
- DNS permet de machines à découvrir le pool frontal ou un serveur Standard Edition server utilisé pour les transactions SIP client.
    
- Il associe des URL simples pour des conférences avec les serveurs hébergeant ces conférences.
    
- Le système DNS permet aux utilisateurs externes et les ordinateurs clients pour se connecter à vos serveurs Edge, ou les proxy inverse HTTP, pour la messagerie instantanée (IM) ou la conférence.
    
- Il permet des communications unifiées (CU) découvrir les périphériques qui ne sont pas enregistrés dans le pool frontal ou un serveur Standard Edition server qui exécute le service web de mise à jour du périphérique pour obtenir des mises à jour et envoyer des journaux.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.
    
- De plus, DNS utilise l’équilibrage de charges.
    
Il est important de noter que Skype pour Business Server 2015 ne prend en charge les noms de domaine internationaux (HMO).
  
Et il est extrêmement important de se rappeler que tous les noms DNS soit identique au nom de l’ordinateur configuré sur un serveur utilisé par Skype pour Business Server 2015. En particulier, nous ne peut pas avoir de tout court des noms dans l’environnement et doit avoir des noms de domaine complets pour le Générateur de topologies.
  
Il semble qu’il serait logique de n’importe quel ordinateur déjà joint à un domaine, mais si vous disposez d’un serveur de transport Edge qui n’est pas lié à votre domaine, il peut avoir une valeur par défaut d’un nom court, par aucun suffixe de domaine. Assurez-vous que n’est pas le cas, soit dans le système DNS ou le serveur de transport Edge ou tout Skype pour Business Server 2015 serveur ou pool, d’ailleurs.
  
Et sans aucun doute n’utilisez pas de caractères Unicode ou des caractères de soulignement. Les caractères standard (qui sont A-Z, a-z, 0-9 et des traits d’union) sont celles qui vont être pris en charge par les serveurs DNS externes et des autorités de certification publiques (vous aurez besoin assigner des noms de domaine complets pour le n° de série du certificat, n’oubliez pas), de sorte que vous aurez de rechange vous-même très compliqué si nom cela à l’esprit.
  
Pour en savoir plus sur les exigences du DNS pour le réseau, consultez la section [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de notre documentation consacrée à la planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des tâches les plus importantes à effectuer avant le déploiement est de vérifier que les certificats sont en ordre. Skype pour Business Server 2015 a besoin d’une infrastructure à clé publique (PKI) pour transport layer security (TLS) et mutuelle (MTLS) connexions TLS. En fait, pour communiquer de manière sécurisée dans une méthode normalisée, Skype pour Business Server utilise les certificats émis par des autorités de certification (AC).
  
Voici certaines des choses que Skype pour Business Server 2015 utilise des certificats pour :
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération utilisant la découverte automatique de partenaires via le DNS
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Communication avec les applications web et Outlook Web Access (OWA)
    
Ainsi, la planification du certificat 's doit. À présent, jetons un œil à une liste de certaines des choses que vous devez garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Skype pour Business Server 2015 prend en charge le SHA-1 et SHA-2 suite du résumé tailles (224, 256, 384 et 512 bits) et satisfait ou dépasse la configuration requise du système d’exploitation.
    
- L’inscription automatique est prise en charge pour les serveurs internes exécutant Skype pour Business Server 2015.
    
- L’inscription automatique n’est pas pris en charge pour Skype pour les serveurs de bord Business Server 2015.
    
- Lorsque vous soumettez une demande de certificat basé sur le web à une autorité de certification Windows Server 2003, vous devez l’envoyer à partir d’un ordinateur exécutant Windows Server 2003 avec Service Pack 2 ou Windows XP.
    
> [!NOTE]
> Bien que l’article de la Base de connaissances Microsoft KB922706 indique comment résoudre les problèmes relatifs à l’inscription de certificats web lors d’une inscription auprès des services de certificat Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat auprès d’une autorité de certification Windows Server 2003. 
  
> [!NOTE]
> L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels.  
  
- Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.
    
- L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
C’est un grand nombre de réfléchir à et sans aucun doute, il existe des différents niveaux de confort avec la demande de certificats auprès d’une autorité de certification. Nous vous donnerons quelques conseils supplémentaires ci-dessous pour rendre votre planification aussi simple que possible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin de certificats pour la plupart de vos serveurs internes, et le plus souvent, vous obtiendrez les à partir d’une autorité de certification interne (ce qui est situé dans votre domaine). Le cas échéant, vous pouvez demander ces certificats à une autorité de certification externe (située sur Internet). Si vous vous demandez quelle autorité de certification publique vous devez atteindre, vous pouvez consulter la liste des [partenaires de certificat de Communications unifiées](https://support.microsoft.com/kb/929395/en-us) .
  
Vous aurez également besoin de certificats lorsque Skype pour Business Server 2015 communique avec d’autres applications et les serveurs, tels que Microsoft Exchange Server. Ce certificat doit bien entendu être un certificat que ces autres applications et serveurs peuvent utiliser en mode de prise en charge. Skype pour Business Server 2015 et d’autres produits Microsoft prennent en charge le protocole d’autorisation ouverte (OAuth) pour l’autorisation et l’authentification de serveur à serveur. Si vous êtes intéressé par cela, nous avons un article de planification supplémentaire pour OAuth et Skype Business Server 2015.
  
Skype pour Business Server 2015 prend également en charge (sans nécessiter) certificats signés à l’aide de la fonction de hachage cryptographique SHA-256. Pour favoriser l’accès externe à l’aide de SHA-256, le certificat externe doit être émis par une autorité de certification publique utilisant SHA-256.
  
Pour tenter de garder les choses simples, nous avons créé les critères des certificats pour les serveurs Standard Edition, les pools de Front-End et les autres rôles, dans les tableaux suivants, avec le contoso.com fictive utilisée pour obtenir des exemples (vous allez probablement utiliser quelque chose Else pour votre environnement). Il s’agit de tous les certificats de serveur web standard, avec des clés privées qui ne sont pas exportables. Quelques points supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Le nom convivial de chaque certificat doit être unique dans le magasin de l’ordinateur.
    
- Comme les exemples de noms ci-dessous, si vous avez configuré des sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, ils doivent être ajoutés pour du certificat sujet Alternative nom (SAN).
    
Certificats pour les serveurs Standard Edition :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=se01.contoso.com ; SAN=se01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur un serveur Standard Edition serveurs Standard Edition server, le nom de domaine complet du serveur est le même que le nom de domaine complet du pool.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> Site web interne • nom de domaine complet (qui est le même que le nom de domaine complet du serveur)  <br/> ET  <br/> • Répondre aux simples URL  <br/> • Accès à distance des URL simple  <br/> • Les URL d’administration simple  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=se01.contoso.com ; SAN=se01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com ; SAN=Admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com ; SAN=se01.contoso.com ; SAN =\*. contoso.com  <br/> |Vous ne pouvez pas substituer le nom de domaine complet dans le Générateur de topologie de site web interne.  <br/> Si vous disposez de plusieurs URL simples de réunion, vous devez les inclure toutes en tant qu’autres noms du sujet (SAN).  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> Web externe de • nom de domaine complet  <br/> ET  <br/> • Accès à distance des URL simple  <br/> • Répondre aux simples URL par domaine SIP  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=se01.contoso.com ; SAN=webcon01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com ; SAN=webcon01.contoso.com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL simples respect, vous devez inclure tous les noms d’objet alternatifs.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour les serveurs frontaux dans un pool frontal :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=eepool.contoso.com ; SAN=eepool.contoso.com ; SAN=ee01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> Site web interne • nom de domaine complet (qui n’est pas le même que le nom de domaine complet du serveur)  <br/> FQDN du serveur •  <br/> • Skype pour le pool d’entreprise nom de domaine complet  <br/> ET  <br/> • Répondre aux simples URL  <br/> • Accès à distance des URL simple  <br/> • Les URL d’administration simple  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=ee01.contoso.com ; SAN=ee01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com ; SAN=Admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com ; SAN=ee01.contoso.com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL simples respect, vous devez inclure tous les noms d’objet alternatifs.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> Web externe de • nom de domaine complet  <br/> ET  <br/> • Accès à distance des URL simple  <br/> • Les URL d’administration simple  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=ee01.contoso.com ; SAN=webcon01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com ; SAN=webcon01.contoso.com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL simples respect, vous devez inclure tous les noms d’objet alternatifs.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool de directeurs  <br/> |Nom de domaine complet du directeur, du nom de domaine complet du pool directeur.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients DNS correspondance stricte requis dans la stratégie de groupe, vous devez également les entrées pour sip.sipdomain (pour chaque domaine SIP que vous avez).  <br/> |pool.contoso.com ; SAN=dir01.contoso.com  <br/> Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et une correspondance DNS stricte est requis dans la stratégie de groupe, vous devez également SAN=sip.contoso.com ; SAN=SIP.fabrikam.com  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> Site web interne • nom de domaine complet (qui est le même que le nom de domaine complet du serveur)  <br/> FQDN du serveur •  <br/> • Skype pour le pool d’entreprise nom de domaine complet  <br/> ET  <br/> • Répondre aux simples URL  <br/> • Accès à distance des URL simple  <br/> • Les URL d’administration simple  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=dir01.contoso.com ; SAN=dir01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com ; SAN=Admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com ; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> Web externe de • nom de domaine complet  <br/> ET  <br/> • Répondre aux simples URL par domaine SIP  <br/> • Accès à distance des URL simple  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |Le nom de domaine complet du directeur externe web doit être différent du pool frontal ou un serveur frontal.  <br/> SN=dir01.contoso.com ; SAN=meet.contoso.com de SAN=directorwebcon01.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com ; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificats de serveur de médiation autonome :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN=medsvr01.contoso .net  <br/> |
   
Certificats pour Survivable Branch Appliance :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appareil  <br/> |SIP. \<sipdomain\> (vous avez besoin qu’une entrée par domaine SIP)  <br/> |.Net de sn=sba01.contoso ; SAN=SIP.contoso.com ; SAN=SIP.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificats pour votre serveur de conversation permanente

Lors de l’installation de votre serveur Chat persistant, vous allez avoir besoin d’un certificat émis par la même autorité de certification que celle utilisée par votre Skype pour les serveurs internes Business Server 2015. Cette opération doit être effectuée pour chaque serveur exécutant persistant Chat Services Web pour téléchargement. Il est vivement recommandé d’avoir l’ou les certificats nécessaire avant de commencer votre installation Chat permanent, et si votre autorité de certification externe, encore plus (le ces éléments peuvent prendre un peu de temps à émettre).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype pour Business Server 2015 prend en charge l’utilisation d’un **seul certificat public** pour l’accès et web conferencing Edge des interfaces externes, ainsi que l’A / V authentification, service qui est fourni par l’ou les serveurs Edge. L’interface interne de bord utilisent généralement un certificat privé émis par votre autorité de certification interne, mais si vous préférez, vous pouvez utiliser un certificat public pour cette ainsi que, s’il s’agit d’une autorité de certification approuvée.
  
Votre proxy inverse (RP) utilise également un certificat public et chiffre la communication de votre RP aux clients et du RP aux serveurs internes via HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez mobilité et vous êtes prenant en charge la découverte automatique pour les clients mobiles, vous aurez besoin d’inclure certaines entrées d’autre nom de sujet supplémentaires sur vos certificats pour prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Quels certificats ? Vous aurez besoin de noms SAN pour la découverte automatique sur les certificats ici :
  
- pool de directeurs
    
- Pool de serveurs frontaux
    
- Proxy inverse
    
Les spécificités sont répertoriées dans chaque tableau ci-dessous.
  
Maintenant, c’est là un peu de planification préalable est bonne, mais parfois vous avez déployé Skype pour Business Server 2015 sans ayant l’intention de déployer la mobilité, et qui apparaît vers le bas la ligne lorsque vous disposez déjà de certificats dans votre environnement. Relance les via une autorité de certification interne est généralement assez facile, mais avec des certificats publics à partir d’une autorité de certification publique, qui peut être un peu plus pricy.
  
Si c’est ce que vous regardez, et si vous avez un grand nombre de domaines SIP (ce qui serait ajoute SAN plus onéreux), vous pouvez configurer votre proxy inverse pour utiliser HTTP pour la requête initiale de Autodiscover Service, au lieu d’utiliser le protocole HTTPS (qui est la valeur par défaut configuration). La rubrique de planification de la mobilité contient plus d’informations à ce sujet.
  
Configuration requise du certificat directeur pool et pool frontal :
  
|**Description**|**Entrée de SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Vous pouvez également utiliser SAN =\*. \<sipdomain\>
  
Exigences relatives au certificat de proxy inverse (autorité de certification publique)
  
|**Description**|**Entrée de SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Ce SAN doit être attribué au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> Continu de votre écouteur proxy inverse pour que les réseaux SAN pour votre URL de Services Web externes. Il peut s’agir SAN=skypewebextpool01.contoso.com et dirwebexternal.contoso.com, si vous avez déployé le directeur, (qui est facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype pour Business Server 2015 est en mesure d’utiliser le même partage de fichiers pour le stockage de tous les fichiers. Gardez à l’esprit ce qui suit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), dont un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. Pour plus d’informations sur DFS pour Windows Server 2012, consultez [cette page DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Nous vous recommandons un cluster partagé pour le partage de fichiers. Si vous effectuez utilisez un, vous devez de cluster Windows Server 2012 R2 ou Windows Server 2012. Windows Server 2008 R2 est également acceptable. Pourquoi le Windows les plus récents ? Les versions antérieures n’est peut-être pas les autorisations pour activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de Cluster pour créer les partages de fichiers, et cet article de [Création d’un Cluster](https://support.microsoft.com/kb/284838) de base de connaissances vous aideront à ces détails.
    
> [!CAUTION]
> Vous devez savoir que le dispositif de stockage réseau (NAS) ne prend pas en charge le partage de fichiers. Vous devez donc utiliser l’une des options proposées ci-après. 
  

