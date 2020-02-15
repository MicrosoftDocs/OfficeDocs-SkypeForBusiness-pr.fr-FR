---
title: Déploiement de la connectivité Skype dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Résumé : Découvrez comment connecter Skype entreprise Server à Skype client. Également appelée connectivité Skype.'
ms.openlocfilehash: be53acc531d0abb789ae4e622a24dc313483cac6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030447"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Déploiement de la connectivité Skype dans Skype entreprise Server

**Résumé :** Découvrez comment connecter Skype entreprise Server avec Skype client. Également appelée connectivité Skype.
  
Cet article décrit le déploiement de la connectivité Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Vue d’ensemble de la connectivité Skype pour les professionnels de l’informatique

La connectivité Skype offre aux utilisateurs de Skype entreprise la possibilité de rechercher et d’ajouter des utilisateurs Skype. La connectivité Skype est une fonctionnalité de Skype entreprise qui vous permet d’activer la Fédération et la recherche dans l’annuaire avec des utilisateurs de Skype. Une fois que vous avez activé la connectivité Skype, vos utilisateurs Skype entreprise pourront rechercher et ajouter des utilisateurs Skype.
  
## <a name="skype-directory-search"></a>Recherche dans l’annuaire Skype

La fonctionnalité de recherche dans l’annuaire Skype permet aux utilisateurs de Skype entreprise de rechercher des contacts Skype. La fonctionnalité de recherche permet aux utilisateurs de rechercher à l’aide des éléments suivants :
  
- **Recherche par nom complet, par exemple « John Doe »** -cela peut retourner de nombreux résultats, vous pouvez donc ne pas trouver ce que vous recherchez.
    
- **Recherche par nom complet plus emplacement, par exemple « John Doe à Barcelone »** -cela réduit considérablement les résultats de la recherche.
    
- **Recherche par courrier électronique, par exemple « JohnDoe@outlook.com »** -cela doit renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement à l’adresse de messagerie spécifiée. Toutefois, si le même message électronique est associé à plusieurs comptes, plusieurs résultats peuvent être renvoyés.
    
- **Recherche par numéro de téléphone, par exemple « 123-123-1234 »,** cela doit renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement au téléphone spécifié. Le numéro de téléphone doit inclure le code du pays (par exemple, 1-xxx-yyy-zzzz). Si le même numéro de téléphone est associé à plusieurs comptes, plusieurs résultats peuvent être renvoyés.
    
- **Recherche par nom Skype, par exemple « JohnDoe1456 »** , si une correspondance exacte est trouvée, elle est renvoyée comme premier résultat. Les autres correspondances « nom » possibles peuvent être renvoyées.
    
    > [!NOTE]
    > La recherche dans l’annuaire Skype doit pouvoir communiquer avec les adresses IP suivantes sur le port 443:104.40.75.246, 23.101.135.34 et 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice de déploiement prise en charge pour la recherche dans l’annuaire Skype

Le tableau suivant décrit la prise en charge de la recherche dans l’annuaire Skype.
  

||**Serveur frontal Skype entreprise Server**|**Serveur frontal Lync Server 2013 (ou plus ancien)**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype entreprise Server Edge  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Skype entreprise Server et Edge sont des conditions préalables pour la recherche dans l’annuaire Skype  <br/> |
|Skype entreprise Server Edge + Lync Server 2013 Edge déployé côte à côte  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Le trafic de recherche dans l’annuaire Skype transite par les serveurs Edge de Skype entreprise Server. Le trafic de Fédération passe par le serveur Edge configuré par l’administrateur. Par exemple, l’administrateur peut choisir de continuer à envoyer le trafic de Fédération via les serveurs Edge Lync Server 2013 qui ne prennent pas en charge la recherche dans l’annuaire Skype.  <br/> |
|Lync Server 2013 (ou plus ancien) Edge  <br/> |Non pris en charge  <br/> |Non pris en charge  <br/> ||
   
> [!NOTE]
> Service AddressBook s’exécutant sur Skype entreprise Server frontal recherche le serveur Edge par l’existence du port de recherche Skype 4443 dans le serveur Edge. 
  
> [!NOTE]
> Si un client dispose de plusieurs sites dans son déploiement local, et s’il a déployé un seul serveur/pool de serveurs Edge Skype entreprise, le trafic de recherche à partir de tous les sites passe par le serveur Edge disponible unique. L’administrateur doit s’assurer que les pools de tous les sites peuvent accéder au pool/serveur Edge de Skype entreprise Server déployé. 
  
> [!NOTE]
> Le service de graphique Skype limite les demandes de recherche à partir de n’importe quel client local ou Office 365 si le taux de demande dépasse 15 demandes/seconde. 
  
> [!NOTE]
> Pour les clients locaux d’entreprise de grande taille, les domaines doivent être la liste d’autorisation du service de recherche Skype afin d’autoriser des taux de demande plus élevés. 
  
> [!NOTE]
> Skype entreprise Server limite les demandes entrantes, s’il y a trop de demandes en attente dans la file d’attente. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Déploiement de la connectivité Skype pour Skype entreprise Online dans Office 365

La connectivité Skype est également une fonctionnalité de Skype entreprise Online, qui fait partie d’Office 365. Vous pouvez activer la fonctionnalité de connectivité Skype à partir du centre d’administration Skype entreprise dans le portail Office 365.
  
Pour Office 365 Midmarket Business, Office 365 Enterprise, Office 365 éducation et Office 365 pour le gouvernement : Connectez-vous au portail Office 365 et accédez au centre d’administration Skype entreprise. Accédez à communications externes. Sous fournisseurs de services de messagerie instantanée publics, cliquez sur Activer. Si vous souhaitez contrôler l’accès des utilisateurs individuels à la connectivité Skype, vous pouvez modifier les paramètres de communications externes des utilisateurs individuels.
  
Pour Office 365 petite entreprise Premium : Connectez-vous à Office 365 et accédez à paramètres \> \> du service d’administration messagerie instantanée, réunions et conférences. Activer les communications externes. Le commutateur communications externes active la connectivité Skype et les communications avec d’autres organisations qui utilisent Skype entreprise.
  
Pour plus d’informations sur l’administration de Skype entreprise Online, voir :
  
- [Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise externes](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Que faire si vous ne pouvez pas utiliser de messagerie instantanée Skype entreprise ou des contacts externes Skype](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Ajouter un contact dans Skype entreprise](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administrateurs : configuration des paramètres de Skype entreprise pour des utilisateurs individuels](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Déploiement de la connectivité Skype pour Skype entreprise Server

Skype entreprise Server utilise l’architecture d’accès à la Fédération pour prendre en charge la connectivité avec Skype. Cette connectivité permet à vos utilisateurs de Skype entreprise Server d’ajouter Skype. Les clients Skype peuvent également ajouter des utilisateurs Skype entreprise à leur liste de contacts. En fonction des stratégies définies de manière administrative dans Skype entreprise Server, les utilisateurs pourront communiquer à l’aide de la messagerie instantanée, consulter leur présence et lancer des appels audio et vidéo. La connectivité Skype est également une fonctionnalité de Skype entreprise Online, qui peut être activée pour les clients Skype entreprise Online à partir du centre d’administration Skype entreprise dans le portail Office 365.
  
> [!NOTE]
> Si Skype entreprise Server est déjà configuré pour se connecter à Windows Messenger à l’aide de la connectivité PIC (public Instant Messaging Connectivity), votre déploiement est déjà configuré pour la connectivité Skype. La seule modification que vous souhaiterez peut-être envisager est de renommer votre entrée Messenger PIC existante comme Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Le site de mise en service de la connectivité PIC de Skype entreprise Server n’est plus disponible.

Le site précédemment utilisé pour approvisionner manuellement la Fédération entre les déploiements locaux de Skype entreprise et Skype n’est plus nécessaire et sera arrêté sur 8/15/2019. La Fédération avec Skype utilise désormais la découverte de partenaire fédéré, qui est le même mécanisme requis pour la Fédération avec Skype entreprise online.

La communication entre tout déploiement Skype entreprise local et les utilisateurs Skype via l’infrastructure de messagerie instantanée publique existante nécessite désormais la compatibilité de la configuration du serveur Edge sur site avec Skype entreprise online.

> [!NOTE]
> Aucune action n’est nécessaire pour la plupart des clients, y compris tous les déploiements qui se fédérer avec Skype entreprise online.
  
Les déploiements locaux sont nécessaires pour publier un enregistrement SRV DNS de Fédération pour chaque domaine qu’il héberge. Des conseils sont disponibles dans la [planification DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Chaque domaine doit être résolu par une requête SRV DNS en un nom de domaine complet de serveur Edge qui répond à une correspondance de suffixe de niveau supérieur du domaine. Par exemple, considérez le domaine « contoso.com » :

|**Noms de domaine complets valides**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Dans chaque cas, le nom de domaine complet exact doit figurer dans le SN ou le SAN du certificat externe installé sur le serveur Edge.   |
|access.contoso.com   ||
|**Noms de domaine complets incorrects**|**Raison**|
|sip.contoso-edge.com   |Pas de correspondance de suffixe.  |
|sip.it.contoso.com   |Pas de correspondance de suffixe de niveau supérieur.   |

Vous trouverez des conseils supplémentaires sur les certificats externes dans la [planification des certificats](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Foires aux questions

**Pourquoi le site Web de mise en service est-il arrêté ?**
Le mécanisme de mise en service PIC (Public IM) (pic.lync.com) déployé dans 2006 n’est plus utilisable et sera arrêté le 8/15/2019. Au lieu de cela, la Fédération de messagerie instantanée publique suppose le même modèle de Fédération que celui utilisé par Skype entreprise Online, connu sous le nom de « découverte de partenaires », par lequel un déploiement sur site est révélé public par son (s) enregistrement (s) SRV DNS de Fédération.

**Cette modification signifie-t-elle que la Fédération de messagerie instantanée publique est déconseillée ?**
Non. La Fédération de messagerie instantanée publique continuera à être prise en charge pendant plusieurs années, jusqu’à ce que le produit Skype entreprise sur site passe en fin de vie.

**Notre société a une relation hybride (espace d’adressage partagé) avec Skype entreprise Online, est-il concernée ?**
Non, étant donné que vous êtes déjà en Fédération avec Skype entreprise Online, cette modification n’aura aucune incidence.
 
**Cette modification signifie-t-elle que notre société doit activer la Fédération avec Skype entreprise Online ?**
Non. Si vos paramètres de proxy de serveur Edge n’activent pas la Fédération avec le fournisseur d’hébergement Skype entreprise Online (sipfed.online.lync.com), cette modification n’affectera pas cette modification. Toutefois, les mêmes exigences de DNS et de certificat qui s’appliquent à la Fédération avec Skype entreprise Online s’appliquent également à la Fédération avec des utilisateurs de Skype.
 
**Notre société est grande et ne peut pas modifier sa configuration Edge en raison des raisons réglementaires/de conformité/etc... que pouvons-nous faire ?**
Toute organisation locale qui ne peut pas modifier sa configuration de serveur Edge comme indiqué doit contacter le support technique dès que possible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la Fédération et de la connectivité PIC (Public IM Connectivity)

Concentrez-vous maintenant sur l’environnement Skype entreprise Server et les tâches administratives requises pour configurer la connectivité Skype. Dans cette section, nous partons du principe que l’administrateur a déployé Skype entreprise Server et configuré l’accès externe, également appelés serveurs Edge. 
  
Trois étapes principales sont nécessaires pour activer la Fédération et PIC. Ce sont les suivants :
  
1. Configuration de la Fédération et de PIC
    
2. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés
    
3. Configurer le paramètre de fournisseur de PIC Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. configurer la Fédération et la PIC

La Fédération est nécessaire pour permettre aux utilisateurs de Skype de communiquer avec les utilisateurs de Skype entreprise au sein de votre organisation. La connectivité PIC (public Instant Messaging Connectivity) est une classe de Fédération et elle doit être configurée pour permettre à vos utilisateurs de Skype entreprise de communiquer avec des utilisateurs de Skype. La Fédération et PIC sont configurés à l’aide du panneau de configuration de Skype entreprise Server.
  
> [!NOTE]
> La Fédération PIC n’est plus prise en charge par les versions de produits antérieures à Lync Server 2010 (Live Communication Server, Office Communications Server). Les plateformes prises en charge pour la Fédération PIC incluent Skype entreprise Server, Lync Server 2013 et Lync Server 2010. 
  
La Fédération est nécessaire pour permettre aux utilisateurs de Skype de communiquer avec les utilisateurs de Skype entreprise au sein de votre organisation. La connectivité PIC (public Instant Messaging Connectivity) est une classe de Fédération et elle doit être configurée pour permettre à vos utilisateurs de Skype entreprise Server de communiquer avec des utilisateurs de Skype. La Fédération et PIC sont configurés à l’aide de la boîte de dialogue Configuration du serveur Edge du panneau de configuration de Skype entreprise Server, comme illustré dans la figure.
  
![Définir un nouveau pool de serveurs Edge](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Les attributs EnableSkypeIdRouting et EnableSkypeDirectorySearch doivent être définis sur true dans les paramètres de fournisseur public (voir les instructions ultérieures) pour que la recherche fonctionne. 
  
Cette opération termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous êtes maintenant configuré pour la connectivité Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide du panneau de configuration de Skype entreprise Server, un administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de Skype peuvent collaborer avec des utilisateurs de Skype entreprise Server internes.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurer le paramètre de fournisseur de PIC Skype

À l’aide de Skype entreprise Server Management Shell, un administrateur doit configurer la stratégie de client Skype entreprise pour qu’elle affiche Skype en tant que fournisseur de PIC supplémentaire. 
  
> [!NOTE]
> Les utilisateurs des fournisseurs de services PIC (public Instant Messaging Connectivity) ne peuvent pas participer à la messagerie instantanée ou aux conférences de votre organisation tant que vous ne configurez pas au moins une stratégie (étape 2, plus haut dans cette procédure), pour prendre en charge la connectivité PIC. 
  
Pour les nouvelles installations, vous pouvez configurer la connectivité Skype en activant un fournisseur public Skype à l’aide du panneau de configuration de Skype entreprise Server, comme illustré dans la figure.
  
![Fournisseurs fédérés SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Pour configurer la connectivité Skype lors de la mise à niveau vers Skype entreprise Server, vous devez supprimer et rajouter le fournisseur public Skype existant. 
  
La configuration de la connectivité Skype peut également être réalisée à l’aide de PowerShell uniquement. Pour configurer la connectivité Skype à l’aide de PowerShell :
  
1. À partir d’un serveur frontal Skype entreprise Server, ouvrez Skype entreprise Server Management Shell.
    
2. Exécutez les deux commandes suivantes :
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un nouveau fournisseur PIC, vous n’avez pas besoin d’exécuter la cmdlet Remove-applet cspublicprovider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Quels sont les paramètres les moins évidents ?
    
   - ProxyFqdn : emplacement du serveur Edge de Fédération Skype (détenu/géré par Microsoft)
    
   - IconURL : icône utilisée par le &amp; client Lync Skype entreprise pour identifier visuellement les contacts Skype
    
   - NameDecorationRoutingDomain et NameDecorationExcludedDomainList : la définition de ces paramètres permet aux utilisateurs d’entrer le MSAs des utilisateurs Skype sans avoir à connaître la « décoration » de domaines non-Microsoft avec « msn.com ». Cela évite de devoir taper « User (contoso. com) @msn. com » pour tous les domaines qui ne sont pas dans le ExcludedDomainList. Le client SfB formatera automatiquement le MSA s’il ne figure pas dans la liste des exclus. Nous avons ajouté les domaines de comptes Microsoft les plus courants à la liste des comptes exclus.
    
     > [!NOTE]
     > Le fournisseur public doit être supprimé et ajouté à nouveau si des modifications sont apportées. Aucune modification sur place n’est autorisée. 
  
     > [!NOTE]
     > Ajouté dans Lync Server 2013 CU5 &amp; client Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation dans laquelle les utilisateurs de Lync ajoutent des contacts Skype nécessaires pour « décorer » des domaines non-Microsoft afin de les identifier et de les acheminer vers Skype (format de : User (contoso. com) @msn. com). Ces nouveaux paramètres autorisent la mise en forme automatique de l’adresse entrée de l’utilisateur dans la boîte de dialogue « Ajouter un contact Skype » avec le NameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines dans le NameDecorationExcludedDomainList ( Nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com). 
  
3. À partir d’un client Skype entreprise, les utilisateurs peuvent désormais Rechercher et ajouter un utilisateur Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matrice des clients et de l’interopérabilité

Le tableau suivant décrit l’état de l’interopérabilité entre la dernière version de Skype Consumer et la dernière version de Skype entreprise.
  

|**Clients Skype**|**Ajouter des contacts, de la messagerie instantanée, de la présence, de l’audio et de la vidéo**|**Comment**|
|:-----|:-----|:-----|
|Bureau Skype Windows  <br/> |7,6 ou supérieur, Windows XP et versions ultérieures  <br/> |**Nouveauté**: prise en charge ajoutée pour le client Skype Windows exécuté sur Windows XP et Windows Vista **(nécessite la dernière version 7,26 ou supérieure du client)** <br/> |
|Skype mobile-téléphone Android et tablette  <br/> |6,19 ou version ultérieure, exécutant le système d’exploitation Android version 4.0.3 ou supérieure  <br/> |Les périphériques à faible spécification ne prennent pas en charge les appels vidéo  <br/> |
|Skype mobile-iOS  <br/> |6,11 ou supérieur, sur IOS 7 ou version ultérieure  <br/> |Non pris en charge : iPhone 4 et versions antérieures, iPod 4ème génération et versions antérieures, iPad 1re génération  <br/> |
|Mac Skype  <br/> |7,19 ou supérieur, sur Mac OS X 10,9 (Mavericks) ou version ultérieure  <br/> |Nécessite Mac OSX 10,9 ou version ultérieure  <br/> |
|Application de bureau et mobile Skype universel Windows (Windows 10)  <br/> |Windows 10 (mise à jour Redstone 1 ou version ultérieure)  <br/> |L’application universelle Windows recevra la mise à jour de automne 2016 en ajoutant la prise en charge de l’interopérabilité  <br/> |
   
Le tableau suivant décrit l’état de l’interopérabilité entre la dernière version de Skype entreprise et la dernière version de Skype client. 
  
|**Client**|**Recherche dans l’annuaire Skype et ajout de contacts**|**Skype A/V, interopérabilité de messagerie instantanée**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui  <br/> |Oui  <br/> |
|Skype Entreprise sur Mac  <br/> |Possibilité d’ajouter (pas de recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2013  <br/> |Possibilité d’ajouter (pas de recherche)  <br/> |Oui  <br/> |
|Lync Web App-en ligne et en local  <br/> |N/A  <br/> |N/A  <br/> |
|Lync mobile-Windows Phone  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync mobile-Android  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync mobile-iOS  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Room System  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Application moderne Lync (Win 8,1)  <br/> |Oui  <br/> |Oui  <br/> |
|Lync Mac 2011  <br/> |Possibilité d’ajouter (pas de recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2010  <br/> |Possibilité d’ajouter (pas de recherche)  <br/> |Oui  <br/> |
|Lync Phone Edition  <br/> |N/A  <br/> |N/A  <br/> |
|Lync Attendant  <br/> |N/A  <br/> |N/A  <br/> |
   

