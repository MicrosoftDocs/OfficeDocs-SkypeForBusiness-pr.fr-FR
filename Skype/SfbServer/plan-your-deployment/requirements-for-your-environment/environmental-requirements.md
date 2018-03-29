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
description: "Summary: Configure your non-server requirements for Skype for Business Server 2015. There are a variety of things you'll want configured before doing your deployment, including Active Directory, DNS, Certs and Fileshares."
ms.openlocfilehash: 0d71140678654442caef112f6132695c76d3ea6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Conditions préalables d’environnement pour Skype Entreprise Server 2015
 
**Summary:** Configure your non-server requirements for Skype for Business Server 2015. There are a variety of things you'll want configured before doing your deployment, including Active Directory, DNS, Certs and Fileshares.
  
What is an environmental requirement for Skype for Business Server 2015? Well, we've put everything that's not directly server related into this topic, so you don't have to do as much clicking around. If you're looking for Server Prerequisites, you can check out the [Server requirements for Skype for Business Server 2015](server-requirements.md) doc.[Networking Planning](../../plan-your-deployment/network-requirements/network-requirements.md) is also documented separately. Otherwise, this is what we've got in this article:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificats](environmental-requirements.md#Certs)
  
- [Partage de fichiers](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

While a lot of configuration data for servers and services is stored in Skype for Business Server 2015's Central Management store, there are some things still stored in Active Directory:
  
|**Active Directory objects**|**Object types**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions for Lync Server 2013 and Lync Server 2010, to maintain backward compatibility with the previous supported versions.  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Contact objects for applications (like the Response Group application and the Conferencing Attendant application).  <br/> |
||Données publiées pour la compatibilité descendante  <br/> |
||A service control point (SCP) for the Central Management store.  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation pour les contrôleurs de domaine

Quel système d’exploitation de contrôleur de domaine faut-il alors utiliser ? Nous avons la liste suivante :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Now, the domain functional level of any domain you deploy Skype for Business Server 2015 into, and the forest functional level of any forest you deploy Skype for Business Server 2015 into, have to be one of the following:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Pouvez-vous avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, dans la mesure où un contrôleur de domaine accessible en écriture est disponible.
  
Now, it's important to know that Skype for Business Server 2015 doesn't support single-labeled domains. Que sont-ils ? If you have a root domain labeled contoso.local, that's going to be fine. If you have a root domain that's just named local, that's not going to work, and it's not supported as a result. A little more about this has been written [in this Knowledge Base article](https://support.microsoft.com/kb/300684/en-us).
  
Skype for Business Server 2015 also doesn't support renaming domains. If you've really got to do that, then you'll need to uninstall Skype for Business Server 2015, do the domain rename, and then reinstall Skype for Business Server 2015.
  
Finally, you may be dealing with a domain with a locked-down AD DS environment, and that's all right. We have more information on how to deploy Skype for Business Server 2015 into that sort of environment in the Deployment docs.
  
### <a name="ad-topologies"></a>Topologies AD

Skype for Business Server 2015's supported topologies are:
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
    
We have diagrams and descriptions to help you determine what topology you have in your environment, or what you may need to set up prior to installing Skype for Business Server 2015. To keep it simple, we're also including a key:
  
![Il s’agit d’une clé pour les icônes utilisées pour les schémas de topologie Skype Entreprise.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Schéma d’une forêt Active Directory unique avec un seul domaine](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
It doesn't get easier than this, it's a single domain forest, this is a common topology.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Schéma d’une forêt unique avec un arbre unique et plusieurs domaines](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme illustre de nouveau une forêt unique, mais elle a un ou plusieurs domaines enfants aussi (il en existe trois dans cet exemple spécifique). So the domain the users are created in might be different from the domain Skype for Business Server 2015 is deployed to. Est-ce problématique ? It's important to remember that when you deploy a Skype for Business Server Front End pool, all the servers in that pool need to be in a single domain. You can have cross-domain administration via Skype for Business Server's support of Windows universal administrator groups.
  
Back to the diagram above, you can see that users from one domain are able to access Skype for Business Server pools from the same domain or from different domains, even if those users are in a child domain.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Schéma d’une forêt unique avec des arbres multiples et des espaces de noms disjoints](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
It may be that you've got a topology similar to this diagram, where you have one forest, but within that forest are multiple domains, with separate AD namespaces. If that's the case, this diagram's a good illustration, as we have users in three different domains accessing Skype for Business Server 2015. Solid lines indicate they're accessing a Skype for Business Server pool in their own domain, while a dashed line indicates they're going to a pool in a different tree altogether.
  
Comme vous pouvez le voir, les utilisateurs dans le même domaine, la même arborescence ou même dans une arborescence différente sont en mesure d’accéder aux pools avec succès.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Schéma de forêts multiples dans une topologie de forêts centralisée](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 does support multiple forests configured in a central forest topology. If you're not sure that's what you have, the central forest in the topology uses objects in it to represent users in the other forests, and hosts user accounts for any users in the forest.
  
Comment cela fonctionne-t-il ? Well, a directory synchronization product (such as Forefront Identity Manager, or FIM) manages your organization's user accounts throughout their existence. Lorsqu’un compte est créé ou supprimé d’une forêt, ce changement est synchronisé avec le contact correspondant dans la forêt centrale.
  
Clearly, if your AD infrastructure is in-place moving to this topology might not be easy, but if you're already there, or still planning out your forest infrastructure, this can be a good choice. You can centralize your Skype for Business Server 2015 deployment within a single forest, while users can search, communicate, and view the presence of other users in any forest. Toutes les mises à jour des contacts utilisateur sont gérées automatiquement à l’aide du logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise
<a name="BKMK_multipleforestopology"> </a>

![Forêts multiples dans un schéma de topologie de forêts de ressources](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
A resource forest topology is also supported; it's where a forest is dedicated to running your server applications, like Microsoft Exchange Server and Skype for Business Server 2015. Cette forêt de ressources héberge également une représentation synchronisée des objets d’utilisateurs actifs, mais aucun compte utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident et ceux-ci ont une relation de confiance au niveau de la forêt avec la forêt de ressources.
  
Note that Exchange Server can be deployed in the same resource forest as Skype for Business Server or in a different forest.
  
To deploy Skype for Business Server 2015 in this type of topology, you'd create one disabled user object in the resource forest for each user account in the user forests (if Microsoft Exchange Server is already in the environment, this might be done for you). Then you'll need a directory synchronization tool (like Forefront Identity Manager, or FIM) to manage user accounts through their life cycle.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à celle décrite dans la rubrique [Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online](environmental-requirements.md#BKMK_multipleforestopology).
  
In this topology, there are one or more user forests, and Skype for Business Server is deployed in a dedicated resource forest. Exchange Server can be deployed on-premises in the same resource forest or a different forest and configured for hybrid with Exchange Online, or email services may be provided exclusively by Exchange Online for the on-premises accounts. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Représente deux forêts AD : une forêt d’utilisateurs et une forêt de ressources. Les deux forêts sont liées par une relation de confiance. Elles sont synchronisées avec Office 365 via Azure AD Connect. Tous les utilisateurs peuvent accéder à Skype Entreprise via Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il existe plusieurs forêts sur site avec une topologie de forêt de ressources. Il existe une relation d’approbation totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser des comptes entre les forêts d’utilisateurs sur site et Office 365.
  
 The organization also has Office 365, and uses [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) to synchronize their on-premises accounts with Office 365. Users who are enabled for Skype for Business are enabled via Office 365 and Skype for Business Online. Skype for Business Server is not deployed on-premises.
  
Single sign-on authentication is provided by an Active Directory Federation Services farm located in the user forest.
  
In this scenario, it is supported to deploy Exchange on-premises, Exchange Online, a hybrid Exchange solution, or to not have Exchange deployed at all. (Le schéma présente uniquement Exchange en local, mais les autres solutions Exchange sont entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources et un déploiement hybride de Skype Entreprise 
<a name="BKMK_multipleforestopology"> </a>

In this scenario, there are one or more on-premises user forests, and Skype for Business is deployed in a dedicated resource forest and is configured for hybrid mode with Skype for Business Online. Exchange Server can be deployed on-premises in the same resource forest or a different forest and may be configured for hybrid with Exchange Online. Alternatively, email services may be provided exclusively by Exchange Online for the on-premises accounts.
  
For more information, see [Configure a multi-forest environment for hybrid Skype for Business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 requires DNS, for the following reasons:
  
- DNS enables Skype for Business Server 2015 to discover internal servers or pools, allowing for server-to-server communications.
    
- DNS allows client machines to discover the Front End pool or Standard Edition server being used for SIP transactions.
    
- Il associe des URL simples pour des conférences avec les serveurs hébergeant ces conférences.
    
- DNS allows external users and client machines to connect to your Edge Servers, or the HTTP reverse proxy, for instant messaging (IM) or conferencing.
    
- It lets unified communications (UC) devices that aren't logged in discover the Front End pool or Standard Edition server that's running the Device Update web service to get updates and send logs.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.
    
- De plus, DNS utilise l’équilibrage de charges.
    
It's important to note that Skype for Business Server 2015 doesn't support internationalized domain names (IDNs).
  
And it's extremely important to remember that any name in DNS be identical to the computer name configured on any server being used by Skype for Business Server 2015. Specifically, we can't have any short-names in the environment, and must have FQDNs for Topology Builder.
  
This seems like it would be logical for any computer already joined to a domain, but if you have an Edge Server that's not joined to your domain, it may have a default of a short name, with no domain suffix. Make sure that's not the case, either in DNS or on the Edge Server, or any Skype for Business Server 2015 server or pool, for that matter.
  
And definitely don't use Unicode characters or underscores. Standard characters (which are A-Z, a-z, 0-9, and hyphens) are the ones that are going to be supported by external DNS and public Certificate Authorities (you'll need to assign FQDNs to the SN in the certificate, don't forget), so you'll spare yourself a lot of grief if you name with this in mind.
  
Pour en savoir plus sur les exigences du DNS pour le réseau, consultez la section [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de notre documentation consacrée à la planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des tâches les plus importantes à effectuer avant le déploiement est de vérifier que les certificats sont en ordre. Skype for Business Server 2015 needs a public key infrastructure (PKI) for transport layer security (TLS) and mutual transport layer security (MTLS) connections. Basically, to communicate securely in a standardized way, Skype for Business Server uses certificates issued by Certificate Authorities (CAs).
  
These are some of the things that Skype for Business Server 2015 uses certificates for:
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération utilisant la découverte automatique de partenaires via le DNS
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Talking to web applications and Outlook Web Access (OWA)
    
So certificate planning's a must. Now, let's look at a list of some of the things you need to keep in mind when requesting certificates:
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Skype for Business Server 2015 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.
    
- Auto-enrollment is supported for internal servers running Skype for Business Server 2015.
    
- Auto-enrollment is not supported for Skype for Business Server 2015 Edge Servers.
    
- When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.
    
> [!NOTE]
> Bien que l’article de la Base de connaissances Microsoft KB922706 indique comment résoudre les problèmes relatifs à l’inscription de certificats web lors d’une inscription auprès des services de certificat Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat auprès d’une autorité de certification Windows Server 2003. 
  
> [!NOTE]
> L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels.  
  
- Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.
    
- L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
So that's a lot to think about, and definitely, there's a variety of comfort levels with requesting certificates from a CA. We'll give you some further guidance below to make your planning as painless as possible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

You'll need certificates for most of your internal servers, and most likely, you'll get them from an internal CA (that's one located in your domain). Le cas échéant, vous pouvez demander ces certificats à une autorité de certification externe (située sur Internet). If you're wondering what public CA you should go to, you can check out the [Unified Communications certificate partners](https://support.microsoft.com/kb/929395/en-us) list.
  
You're also going to need certificates when Skype for Business Server 2015 communicates with other applications and servers, such as Microsoft Exchange Server. Ce certificat doit bien entendu être un certificat que ces autres applications et serveurs peuvent utiliser en mode de prise en charge. Skype for Business Server 2015 and other Microsoft products support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization. If you're interested in this, we have an additional planning article for OAuth and Skype for Business Server 2015.
  
Skype for Business Server 2015 also includes support for (without requiring) certificates signed using the SHA-256 cryptographic hash function. Pour favoriser l’accès externe à l’aide de SHA-256, le certificat externe doit être émis par une autorité de certification publique utilisant SHA-256.
  
To try and keep things straightforward, we've put the certificate requirements for Standard Edition servers, Front End pools, and other roles, into the following tables, with the fictional contoso.com being used for examples (you'll probably be using something else for your environment). Il s’agit de tous les certificats de serveur web standard, avec des clés privées qui ne sont pas exportables. Quelques points supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Le nom convivial de chaque certificat doit être unique dans le magasin de l’ordinateur.
    
- As per the sample names below, if you've configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, they need to be added to the certificate's Subject Alternative Name (SAN).
    
Certificates for Standard Edition servers:
  
|**Certificate**|**Subject name/Common name**|**Subject alternative name**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |On Standard Edition servers Standard Edition server, the server FQDN is the same as the pool FQDN.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Internal web FQDN (which is the same as the FQDN of the server)  <br/> ET  <br/> • Meet simple URLs  <br/> • Dial-in simple URL  <br/> • Admin simple URL  <br/> OU  <br/> • A wildcard entry for the simple URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com  <br/> |You can't override the Internal web FQDN in Topology Builder.  <br/> Si vous disposez de plusieurs URL simples de réunion, vous devez les inclure toutes en tant qu’autres noms du sujet (SAN).  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • External web FQDN  <br/> ET  <br/> • Dial-in simple URL  <br/> • Meet simple URLs per SIP domain  <br/> OU  <br/> • A wildcard entry for the simple URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |If you have multiple Meet simple URLs, you've got to include all of them as subject alternative names.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificates for Front End Servers in a Front End pool:
  
|**Certificate**|**Subject name/Common name**|**Subject alternative name**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Internal web FQDN (which is NOT the same as the FQDN of the server)  <br/> • Server FQDN  <br/> • Skype for Business pool FQDN  <br/> ET  <br/> • Meet simple URLs  <br/> • Dial-in simple URL  <br/> • Admin simple URL  <br/> OU  <br/> • A wildcard entry for the simple URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com  <br/> |If you have multiple Meet simple URLs, you've got to include all of them as subject alternative names.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • External web FQDN  <br/> ET  <br/> • Dial-in simple URL  <br/> • Admin simple URL  <br/> OU  <br/> • A wildcard entry for the simple URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |If you have multiple Meet simple URLs, you've got to include all of them as subject alternative names.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificates for the Director:
  
|**Certificate**|**Subject name/Common name**|**Subject alternative name**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool de directeurs  <br/> |FQDN of the Director, FQDN of the Director pool.  <br/> If this pool is the auto-logon server for clients and strict DNS matching's required in group policy, you'll also need entries for sip.sipdomain (for each SIP domain you have).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Internal web FQDN (which is the same as the FQDN of the server)  <br/> • Server FQDN  <br/> • Skype for Business pool FQDN  <br/> ET  <br/> • Meet simple URLs  <br/> • Dial-in simple URL  <br/> • Admin simple URL  <br/> OU  <br/> • A wildcard entry for the simple URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • External web FQDN  <br/> ET  <br/> • Meet simple URLs per SIP domain  <br/> • Dial-in simple URL  <br/> OU  <br/> • A wildcard entry for the simple URLs  <br/> |The Director external web FQDN must be different from the Front End pool or Front End Server.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com  <br/> |
   
Certificates for Stand-alone Mediation Server:
  
|**Certificate**|**Subject name/Common name**|**Subject alternative name**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificates for Survivable Branch Appliance:
  
|**Certificate**|**Subject name/Common name**|**Subject alternative name**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appareil  <br/> |SIP.\<sipdomain\> (you need only one entry per SIP domain)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificats pour votre serveur de conversation permanente

When installing your Persistent Chat Server, you're going to need a certificate that's issued by the same CA as the one used by your Skype for Business Server 2015 internal servers. This needs to be done for each server running the Persistent Chat Web Services for File Upload/Download. We highly recommend you have the required certificate(s) before you start your Persistent Chat installation, and if your CA is external, even more so (these things can take a little time to be issued).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype for Business Server 2015 supports the use of a **single public certificate** for access and web conferencing Edge external interfaces, plus the A/V Authentication service, which is all provided via the Edge Server(s). Your Edge internal interface will typically use a private certificate issued by your internal CA, but if you'd prefer, you can use a public certificate for this as well, if it's from a trusted CA.
  
Votre proxy inverse (RP) utilise également un certificat public et chiffre la communication de votre RP aux clients et du RP aux serveurs internes via HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

If you're deploying mobility and you're supporting automatic discovery for mobile clients, you're going to need to include some additional subject alternate name entries on your certificates to support the secure connections from the mobile clients.
  
Quels certificats ? Vous aurez besoin de noms SAN pour la découverte automatique sur les certificats ici :
  
- pool de directeurs
    
- Pool de serveurs frontaux
    
- Proxy inverse
    
Les spécificités sont répertoriées dans chaque tableau ci-dessous.
  
Now, this is where a little pre-planning is good, but sometimes you've deployed Skype for Business Server 2015 without intending to deploy mobility, and that comes up down the line when you already have certificates in your environment. Reissuing them via an internal CA is typically pretty easy, but with public certificates from a public CA, that can be a little more pricy.
  
If that's what you're looking at, and if you have a lot of SIP domains (which would make adding SANS more expensive), you can configure your reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (which is the default configuration). La rubrique de planification de la mobilité contient plus d’informations à ce sujet.
  
Director pool and Front End pool certificate requirements:
  
|**Description**|**SAN entry**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
You can alternatively use SAN=\*.\<sipdomain\>
  
Exigences relatives au certificat de proxy inverse (autorité de certification publique)
  
|**Description**|**SAN entry**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Ce SAN doit être attribué au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> Your reverse proxy listener's going to have SANs for your external Web Services URL(s). Some examples would be SAN=skypewebextpool01.contoso.com and dirwebexternal.contoso.com, if you've deployed the Director, (which is optional). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype for Business Server 2015 is able to use the same file share for all file storage. Gardez à l’esprit ce qui suit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), dont un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. For further reading on DFS for Windows Server 2012, check out [this DFS page](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- We recommend a shared cluster for the file share. If you're using one, you should cluster Windows Server 2012 or Windows Server 2012 R2. Windows Server 2008 R2 is acceptable as well. Why the latest Windows? Older versions may not have the right permissions to enable all features. You can use Cluster Administrator to create the file shares, and this [Creating a Cluster](https://support.microsoft.com/kb/284838) KB article will help you with those details.
    
> [!CAUTION]
> Vous devez savoir que le dispositif de stockage réseau (NAS) ne prend pas en charge le partage de fichiers. Vous devez donc utiliser l’une des options proposées ci-après. 
  

