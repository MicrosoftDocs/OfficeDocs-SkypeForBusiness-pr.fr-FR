---
title: Déployer Skype connectivité dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Résumé : Découvrez comment se connecter à Skype Entreprise Server client Skype client. Également appelée Skype de connexion.'
ms.openlocfilehash: 467d87968e7e5b0357e8d23b578a511adb281e27
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729883"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Déployer Skype connectivité dans Skype Entreprise Server

**Résumé :** Découvrez comment connecter Skype Entreprise Server client Skype client. Également appelée Skype de connexion.
  
Cet article décrit le déploiement de Skype Connectivity.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Vue d’ensemble de la connectivité pour les professionnels de l’informatique

Skype La connectivité permet Skype Entreprise utilisateurs de rechercher et d’ajouter des Skype utilisateurs. Skype La connectivité est une fonctionnalité de Skype Entreprise qui vous permet d’activer la fédération et la recherche dans l’annuaire avec Skype utilisateurs. Une fois que vous avez Skype la connectivité Skype Entreprise utilisateurs de votre entreprise pourront rechercher et ajouter des Skype utilisateurs.
  
## <a name="skype-directory-search"></a>Skype Recherche dans l’annuaire

Skype La fonctionnalité de recherche dans l’Skype Entreprise permet aux utilisateurs de rechercher Skype contacts. La fonctionnalité de recherche permet aux utilisateurs d’effectuer des recherches à l’aide des fonctionnalités suivantes :
  
- **Recherche par nom d’affichage, par exemple** « John Doe » : cela peut renvoyer de nombreux résultats, de sorte que vous ne trouvez peut-être pas ce que vous recherchez.
    
- **Recherche par nom d’affichage plus emplacement,** par exemple « John Doe à Domaine » : cela réduit considérablement les résultats de la recherche.
    
- **Recherche par courrier électronique, par exemple « johndoe@outlook.com** » : cela doit renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement à l’e-mail spécifié. Toutefois, si le même e-mail est associé à plusieurs comptes, plusieurs résultats peuvent être renvoyés.
    
- Recherche par numéro de téléphone, par exemple **« 123-123-1234** », qui doit renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement au téléphone spécifié. Téléphone numéro doit inclure le code du pays (c’est-à-dire 1-xxx-yyy-zzzz). Si le même numéro de téléphone est associé à plusieurs comptes, plusieurs résultats peuvent être renvoyés.
    
- Recherchez par Skype, par exemple « **JohnDoe1456** » : si une correspondance exacte est trouvée, elle sera renvoyée en tant que premier résultat. D’autres correspondances de « nom » possibles peuvent être renvoyées.
    
    > [!NOTE]
    > Skype La recherche dans l’annuaire doit pouvoir communiquer avec les adresses IP suivantes sur le port 443 : 104.40.75.246, 23.101.135.34 et 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice de déploiement prise en charge Skype recherche dans l’annuaire

Le tableau suivant décrit la prise en charge de Skype recherche dans l’annuaire.
  

||**Skype Entreprise Server Frontal**|**Serveur frontal Lync Server 2013 (ou plus ancien)**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Server Edge  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Skype Entreprise Server et Edge sont des conditions préalables pour Skype recherche dans l’annuaire  <br/> |
|Skype Entreprise Server Edge + Lync Server 2013 Edge déployé côte à côte  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Skype Le trafic de recherche dans l’annuaire passe par Skype Entreprise Server serveurs Edge. Le trafic de fédération passe par edge configuré par l’administrateur. Par exemple, l’administrateur peut décider de continuer à envoyer le trafic de fédération via les serveurs Edge Lync Server 2013 qui ne pourraient pas prendre en charge Skype recherche dans l’annuaire.  <br/> |
|Serveur Edge Lync Server 2013 (ou plus ancien)  <br/> |Non pris en charge  <br/> |Non pris en charge  <br/> ||
   
> [!NOTE]
> Le service de carnet d’adresses Skype Entreprise Server frontal recherche le serveur Edge en fonction de l’existence du port Skype Search 4443 sur le serveur Edge. 
  
> [!NOTE]
> Dans le cas où un client possède plusieurs sites dans son déploiement local et s’il n’a déployé qu’un seul serveur edge/pool Skype Entreprise Server, le trafic de recherche de tous les sites passe par le serveur Edge disponible unique. L’administrateur doit s’assurer que les pools de tous les sites peuvent accéder au Skype Entreprise Server/pool Edge déployé. 
  
> [!NOTE]
> Skype service graph limitera les demandes de recherche provenant d’un client local ou Microsoft 365 ou Office 365 si le taux de demandes dépasse 15 demandes/seconde. 
  
> [!NOTE]
> Pour les clients locaux de grande entreprise, les domaines doivent être ajoutés à une liste d’utilisateurs avec le service de recherche Skype pour permettre des taux de demandes plus élevés.
  
> [!NOTE]
> Skype Entreprise Server les demandes entrantes, s’il y a trop de demandes en attente dans la file d’attente. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Déploiement de Skype connectivity pour Skype Entreprise Online

Skype La connectivité est également une fonctionnalité de Skype Entreprise Online, qui fait partie de Microsoft 365 et Office 365. Vous pouvez activer la fonctionnalité Skype connectivité à partir du centre d Skype Entreprise’administration dans le Centre d’administration Microsoft 365.
  
Pour Microsoft 365 moyenne entreprise, Office 365 Entreprise, Microsoft 365 Éducation et Office 365 pour le gouvernement : connectez-vous au Centre d’administration Microsoft 365 et accédez au Centre d’administration Skype Entreprise. Go to External Communications. Sous Fournisseurs de services de messagerie instantanée publics, cliquez sur Activer. Si vous souhaitez contrôler l’accès des utilisateurs individuels à Skype connectivité, vous pouvez le faire en éditant les paramètres de communications externes des utilisateurs individuels.
  
Pour Office 365 Petite Entreprise Premium : connectez-vous à Office 365, puis Paramètres service d’administration pour la messagerie instantanée, les réunions et \> \> les conférences. Activer les communications externes. Le commutateur de communications externes Skype la connectivité et les communications avec d’autres organisations qui utilisent Skype Entreprise.
  
Pour plus d’informations sur Skype Entreprise Administration en ligne, voir :
  
- [Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise externes](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Ce qu’il faut essayer si vous ne pouvez pas Skype Entreprise messagerie instantanée Skype contacts externes](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Ajouter un contact dans Skype Entreprise](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administrateurs : configurer les paramètres Skype Entreprise utilisateurs individuels](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Déploiement de Skype connectivité pour Skype Entreprise Server

Skype Entreprise Server utilise l’architecture d’accès de fédération pour prendre en charge la connectivité avec Skype. Cette connectivité permet à vos utilisateurs Skype Entreprise Server d’ajouter des Skype. Skype clients peuvent également ajouter Skype Entreprise utilisateurs à leur liste de contacts. En fonction des stratégies définies administrativement dans Skype Entreprise Server les utilisateurs pourront communiquer à l’aide de la messagerie instantanée, voir la présence des autres utilisateurs et lancer des appels audio et vidéo. Skype connectivité est également une fonctionnalité de Skype Entreprise Online et peut être activée pour les clients Skype Entreprise Online à partir du Centre d’administration Skype Entreprise au sein du Centre d’administration Microsoft 365.
  
> [!NOTE]
> Si Skype Entreprise Server est déjà configuré pour se connecter à Windows Messenger à l’aide de la connectivité PIC (Public Instant Messaging Connectivity), votre déploiement est déjà configuré pour Skype connectivité. La seule modification que vous souhaitez peut-être prendre en compte est de renommer votre entrée Messenger PIC existante en tant que Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Le Skype Entreprise Server de mise en service de la connectivité de messagerie instantanée publique n’est plus disponible

Le site qui était auparavant utilisé pour mettre en service manuellement la fédération entre les déploiements locaux Skype Entreprise et Skype n’est plus nécessaire et sera arrêté le 15/08/2019. La fédération avec Skype utilise désormais la découverte de partenaires fédérés, qui est le même mécanisme requis pour la fédération avec Skype Entreprise Online.

La communication entre tout déploiement Skype Entreprise local et les utilisateurs Skype via l’infrastructure de messagerie instantanée publique existante nécessite désormais que la configuration du serveur Edge local soit compatible avec Skype Entreprise Online.

> [!NOTE]
> Aucune action n’est nécessaire pour la plupart des clients, y compris tous les déploiements fédérés avec Skype Entreprise Online.
  
Les déploiements locaux sont nécessaires pour publier un enregistrement SRV DNS de fédération pour chaque domaine qu’ils hébergent. Des conseils sont disponibles dans la [planification DNS.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Chaque domaine doit être résolu par une requête DNS SRV vers un nom de domaine pleinement attribué au serveur Edge qui satisfait à une correspondance de suffixe de niveau supérieur du domaine. Par exemple, considérez le domaine « contoso.com » :

|**FQDNs valides**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Dans chaque cas, le nom deqdn exact doit être présent dans le SN ou le SAN du certificat externe installé sur le serveur Edge.   |
|access.contoso.com   ||
|**FQDNs non valides**|**Raison**|
|sip.contoso-edge.com   |Il ne s’agit pas d’une correspondance de suffixe.  |
|sip.it.contoso.com   |Il ne s’agit pas d’une correspondance de suffixe de niveau supérieur.   |

Vous pouvez trouver des instructions supplémentaires concernant les certificats externes dans [la planification des certificats.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>FAQ

**Pourquoi le site web d’approvisionnement est-il arrêté ?**
Le mécanisme d’approvisionnement PIC (Public IM Provisioning Mechanism) (pic.lync.com) qui a été déployé en 2006 n’est plus utilisable et sera arrêté le 15/08/2019. Au lieu de cela, la fédération de messagerie instantanée publique suppose le même modèle de fédération que celui utilisé par Skype Entreprise Online, appelé « découverte de partenaires », dans lequel un déploiement local est publiquement découvrable par ses enregistrement(s) SRV DNS de fédération.

**Cette modification signifie-t-elle que la fédération de messagerie instantanée publique est en cours d’precaté ?**
Non. La fédération de messagerie instantanée publique continuera d’être prise en charge pendant de nombreuses années, probablement jusqu’à ce que Skype Entreprise produit local atteigne la fin de vie.

**Notre entreprise a une relation hybride (espace d’adressas partagé) avec Skype Entreprise Online, sommes-nous affectés ?**
Non, étant donné que vous êtes déjà fédéré avec Skype Entreprise Online, cette modification ne vous affectera pas.
 
**Cette modification signifie-t-elle que notre entreprise doit activer la fédération avec Skype Entreprise Online ?**
Non. Si les paramètres de proxy de votre serveur Edge n’activent pas la fédération avec le fournisseur d’hébergement Skype Entreprise Online (sipfed.online.lync.com), cette modification n’affectera pas ce paramètre. Toutefois, les mêmes exigences en matière de DNS et de certificats qui s’appliquent maintenant à la fédération avec Skype Entreprise Online s’appliquent également à la fédération avec Skype utilisateurs.
 
**Notre entreprise est de grande taille et ne peut pas modifier sa configuration edge pour des raisons réglementaires/de conformité/etc... Que pouvons-nous faire ?**
Toute organisation sur site qui ne peut pas modifier sa configuration de serveur Edge comme spécifié doit atteindre le support technique au plus tôt.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la fédération et de la connectivité PIC (Public IM Connectivity)

À présent, concentrez-vous sur l Skype Entreprise Server et les tâches administratives requises pour configurer Skype connectivité. Dans cette section, nous partons du principe que l’administrateur a déployé Skype Entreprise Server et configuré l’accès externe, également appelé serveurs Edge. 
  
Trois étapes principales sont requises pour activer la fédération et pic. Il s’agit des éléments suivants :
  
1. Configurer la fédération et pic
    
2. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés
    
3. Configurer le paramètre Skype fournisseur PIC
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurer la fédération et pic

La fédération est nécessaire pour permettre aux utilisateurs Skype de communiquer avec Skype Entreprise utilisateurs de votre organisation. La connectivité PIC (Public Instant Messaging Connectivity) est une classe de fédération et elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise de communiquer avec Skype utilisateurs. La fédération et pic sont configurés à l’aide Skype Entreprise Server panneau de configuration.
  
> [!NOTE]
> La fédération PIC n’est plus prise en charge par les lancements de produits antérieurs à Lync Server 2010 (Live Communication Server, Office Communications Server). Les plateformes pris en charge pour la fédération PIC incluent Skype Entreprise Server, Lync Server 2013 et Lync Server 2010. 
  
La fédération est nécessaire pour permettre aux utilisateurs Skype de communiquer avec Skype Entreprise utilisateurs de votre organisation. La connectivité PIC (Public Instant Messaging Connectivity) est une classe de fédération et elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise Server de communiquer avec Skype utilisateurs. La fédération et pic sont configurés à l’aide de la boîte de dialogue de configuration Edge du panneau Skype Entreprise Server de configuration, comme illustré dans la figure.
  
![Définissez un nouveau pool edge.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Les attributs EnableSkypeIdRouting et EnableSkypeDirectorySearch doivent être définies sur true dans les paramètres du fournisseur public (voir les instructions ultérieures) pour que la recherche fonctionne. 
  
Cette procédure termine les tâches administratives qui doivent être effectuées sur le serveur. Vous êtes maintenant prêt pour Skype connectivité.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide Skype Entreprise Server panneau de configuration, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs Skype peuvent collaborer avec des utilisateurs Skype Entreprise Server internes.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurer le paramètre Skype fournisseur PIC

À l’aide Skype Entreprise Server Management Shell, un administrateur doit configurer la stratégie de client Skype Entreprise pour afficher Skype en tant que fournisseur PIC supplémentaire. 
  
> [!NOTE]
> Les utilisateurs des fournisseurs de services PIC (Public Instant Messaging Connectivity) ne peuvent pas participer à des conférences ou des messages instantanés dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2, plus haut dans cette procédure) pour prendre en charge la connectivité PIC. 
  
Pour les nouvelles installations, vous pouvez configurer Skype Connectivity en activant un fournisseur public Skype à l’aide du Panneau de configuration Skype Entreprise Server, comme illustré dans la figure.
  
![Fournisseurs fédérés SIP.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Pour configurer la Skype lors de la mise à niveau vers Skype Entreprise Server vous devez supprimer et rajouter le fournisseur public Skype existant. 
  
La configuration Skype la connectivité peut également être effectuée à l’aide de PowerShell uniquement. Pour configurer la Skype à l’aide de PowerShell :
  
1. À partir d Skype Entreprise Server serveur frontal, ouvrez Skype Entreprise Server Management Shell.
    
2. Exécutez les deux commandes suivantes :
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un fournisseur PIC, vous n’avez pas besoin d’exécuter la cmdlet Remove-CsPublicProvider de messagerie. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Que font les paramètres moins évidents ?
    
   - ProxyFqdn : emplacement du Skype de fédération (propriété/gestion par Microsoft)
    
   - IconURL : icône utilisée par le client Skype Entreprise Lync pour identifier &amp; visuellement Skype contacts
    
   - NameDecorationRoutingDomain et NameDecorationExcludedDomainList : la définition de ces paramètres permet aux utilisateurs d’entrer les MSA des utilisateurs de Skype sans avoir à connaître la « décoration » des domaines non-Microsoft avec « msn.com ». Cela élimine la nécessité de taper « user(contoso.com)@msn.com » pour tous les domaines qui ne sont PAS dans excludedDomainList. Le client SfB formate automatiquement le compte MSA si le domaine n’est PAS dans la liste des domaines exclus. Nous avons ajouté les domaines de compte Microsoft les plus courants à la liste des domaines exclus.
    
     > [!NOTE]
     > Si des modifications sont apportées, le fournisseur public doit être supprimé et ajouté. Aucune modification sur place n’est autorisée. 
  
     > [!NOTE]
     > Ajouté dans le client de bureau Lync Lync 2013 CU5 dans &amp; Office 2013 SP1, nameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation dans laquelle les utilisateurs Lync ajoutent des contacts Skype nécessaires à la « décoration » des domaines non-Microsoft pour les identifier et les router vers Skype (format : user(contoso.com)@msn.com). Ces nouveaux paramètres autorisent la mise en forme automatique de l’entrée de l’utilisateur d’adresse dans la boîte de dialogue « Ajouter un contact de Skype » avec nameDecorationRoutingDomain (qui doit être définie sur msn.com) s’il ne contient pas les domaines dans la liste NameDecorationExcludedDomainList (nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com). 
  
3. À partir d Skype Entreprise utilisateurs clients peuvent désormais rechercher et ajouter un Skype utilisateur.
    
## <a name="clients-and-interoperability-matrix"></a>Clients et matrice d’interopérabilité

Le tableau suivant décrit l’état de l’interopération entre la dernière version du consommateur Skype et la dernière version de Skype Entreprise.
  

|**Skype Clients**|**Ajouter des contacts, la messagerie instantanée, la présence, l’audio et les appels vidéo**|**Comment**|
|:-----|:-----|:-----|
|Skype Windows Bureau  <br/> |7.6 ou supérieure, Windows XP et supérieur  <br/> |**NOUVEAU**: prise en charge ajoutée pour Windows Skype client s’exécutant sur Windows XP et Windows Vista (nécessite la **dernière version du client 7.26 ou version supérieure)** <br/> |
|Skype Mobile - Android Téléphone et tablette  <br/> |Version 6.19 ou supérieure, exécutant Android OS version 4.0.3 ou supérieure  <br/> |Les périphériques à faible spécification peuvent ne pas prendre en charge les appels vidéo  <br/> |
|Skype Mobile - iOS  <br/> |6.11 ou supérieur, sur IOS 7 ou supérieur  <br/> |Non pris en charge iPhone 4 et antérieures, iPod 4e génération et iPad 1re génération  <br/> |
|Skype Mac  <br/> |7.19 ou supérieur, sur Mac OS X 10.9 (Contrôles) ou supérieur  <br/> |Nécessite Mac OSX 10.9 ou supérieur  <br/> |
|Skype Universal Windows App (Windows 10) Desktop and Mobile  <br/> |Windows 10 (mise à jour de Redstone 1 ou version ultérieure)  <br/> |Windows L’application universelle recevra la mise à jour à l’automne 2016, ce qui ajoutera la prise en charge de l’interop.  <br/> |
   
Le tableau suivant décrit l’état de l’interopération entre la dernière version de Skype Entreprise et la dernière version de Skype client. 
  
|**Client**|**Skype Recherche dans l’annuaire et ajout de contacts**|**Skype A/V, iop de messagerie instantanée**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui  <br/> |Oui  <br/> |
|Skype Entreprise sur Mac  <br/> |Peut ajouter (aucune recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2013  <br/> |Peut ajouter (aucune recherche)  <br/> |Oui  <br/> |
|Lync Web App : en ligne et en local  <br/> |N/A  <br/> |N/A  <br/> |
|Lync Mobile - Windows Phone  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Mobile - Android  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Mobile - iOS  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Room System  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Oui  <br/> |Oui  <br/> |
|Lync Mac 2011  <br/> |Peut ajouter (aucune recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2010  <br/> |Peut ajouter (aucune recherche)  <br/> |Oui  <br/> |
|Lync Phone Edition  <br/> |N/A  <br/> |N/A  <br/> |
|Lync Attendant  <br/> |N/A  <br/> |N/A  <br/> |
   
