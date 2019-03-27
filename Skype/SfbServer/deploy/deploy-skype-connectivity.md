---
title: Déployer une connectivité Skype dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Résumé : Découvrez comment connecter Skype pour Business Server Skype consommateur. Également appelé Skype connectivité.'
ms.openlocfilehash: 3dd48661b230f4e780505be4aeb05bbe9ff82340
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874506"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Déployer une connectivité Skype dans Skype pour Business Server
 
**Résumé :** Découvrez comment connecter Skype pour Business Server Skype consommateur. Également appelé Skype connectivité.
  
Cet article décrit le déploiement de la connectivité Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Vue d’ensemble de la connectivité Skype pour les professionnels de l’informatique

Connectivité Skype fournit Skype pour les utilisateurs professionnels avec la possibilité de rechercher et ajouter des utilisateurs de Skype. Connectivité Skype est une fonctionnalité de Skype pour les entreprises qui vous permet d’activer la fédération et le répertoire de recherche avec des utilisateurs de Skype. Après avoir activé la connectivité Skype votre Skype pour les utilisateurs pourront rechercher et ajouter des utilisateurs de Skype.
  
## <a name="skype-directory-search"></a>Recherche dans l’annuaire Skype

La fonctionnalité Recherche dans l’annuaire Skype permet aux utilisateurs de Skype Entreprise de rechercher des contacts Skype. La fonctionnalité de recherche permet aux utilisateurs de rechercher des utilisateurs comme suit :
  
- **Rechercher par nom complet, exemple « Jean Dupont »** - ce peut renvoyer le nombre de résultats, afin que vous pouvez ne pas trouverez ce que vous recherchez.
    
- **Rechercher par nom complet et emplacement, exemple « John Doe dans Barcelone »** - Cela permet de restreindre les résultats de la recherche considérablement vers le bas.
    
- **Recherche par courrier électronique, exemple de « johndoe@outlook.com »** - il doit renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement à la messagerie spécifié. Mais si le même e-mail est associé à plusieurs comptes, plusieurs résultats peuvent être retournés.
    
- **Rechercher par numéro de téléphone, exemple de « 123-123-1234 »** - il doit renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement à un téléphone spécifié. Le numéro de téléphone doit inclure le code du pays (à savoir, 1-xxx-yyy-zzzz). Si le même numéro de téléphone est associé à plusieurs comptes, plusieurs résultats peuvent être retournés.
    
- **Recherche par nom Skype, par exemple « JohnDoe1456 »** - si une correspondance exacte est trouvée, elle est renvoyée comme premier résultat. Autres correspondances possibles « name » peuvent être retournées.
    
    > [!NOTE]
    > La recherche dans l’annuaire Skype doit pouvoir communiquer avec les adresses IP suivantes sur le port 443 : 104.40.75.246, 23.101.135.34 et 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice de déploiement prise en charge pour la Recherche dans l’annuaire Skype

Le tableau suivant présente la prise en charge pour la Recherche dans l’annuaire Skype.
  

||**Skype pour Business Server frontal**|**Serveur frontal Lync Server 2013 (ou antérieur)**|**Commentaires**|
|:-----|:-----|:-----|:-----|
|Skype pour Business serveur Edge  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Skype pour Business Server et Edge sont les conditions requises pour la recherche dans l’annuaire Skype  <br/> |
|Skype pour le serveur Edge Server Business + serveur Edge Lync Server 2013 déployée côte à côte  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Le flux de la recherche dans l’annuaire Skype transite par les serveurs de Skype Entreprise Server Edge. Le flux de fédération passe à travers le serveur Edge configuré par l’administrateur. Par exemple, l’administrateur peut choisir de continuer à envoyer le trafic de fédération via les serveurs Edge Lync Server 2013 qui ne prennent pas en charge la recherche dans l’annuaire Skype.  <br/> |
|Serveur Edge Lync Server 2013 (ou antérieur)  <br/> |Non pris en charge  <br/> |Non pris en charge  <br/> ||
   
> [!NOTE]
> Service de carnet d’adresses en cours d’exécution sur Skype pour Business Server frontal recherche le bord à l’existence du port Skype recherche 4443 dans le serveur de périphérie. 
  
> [!NOTE]
> Si un client a plusieurs sites dans leur déploiement sur site, et si elles ont déployé qu’un seul Skype pour serveur/pool d’entreprise serveur Edge, puis recherchez le trafic en provenance de tous les sites est dirigés via le serveur de périphérie unique disponible. L’administrateur doit s’assurer que les pools de tous les sites peuvent accéder à la Skype pour serveur/pool d’entreprise serveur Edge déployé. 
  
> [!NOTE]
> Le service graphique de Skype limite les demandes de recherche émanant de tout site local ou client Office 365 si le taux de demandes dépasse 15 demandes par seconde. 
  
> [!NOTE]
> Pour les clients sur sites locaux des grandes entreprises, les domaines doivent être placés sur liste blanche auprès du service de recherche Skype pour permettre des taux de demandes plus élevés. 
  
> [!NOTE]
> Skype pour Business Server limiter les demandes entrantes, s’il y a trop de demandes en attente dans la file d’attente. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Déploiement de la connectivité Skype pour Skype Entreprise Online dans Office 365

La connectivité Skype est également une fonctionnalité de Skype Entreprise Online, qui fait partie d’Office 365. Vous pouvez activer la fonctionnalité de connectivité Skype à partir du centre d’administration Skype Entreprise dans le portail Office 365.
  
Pour Office 365 Moyenne Entreprise, Office 365 Entreprise, Office 365 Éducation et Office 365 pour le Secteur public : connectez-vous au portail Office 365 et accédez au centre d’administration Skype Entreprise. Accédez à Communications externes. Sous Fournisseurs de service de messagerie instantanée publique, cliquez sur Activer. Si vous souhaitez contrôler l’accès des utilisateurs individuels à la connectivité Skype, vous pouvez le faire en modifiant les paramètres de communication externe des utilisateurs individuels.
  
Pour Office 365 petite entreprise Premium : Se connecter à Office 365 et accédez à Admin \> paramètres du Service \> des réunions de messagerie, instantanées et conférence. Activez les communications externes. Le commutateur Communications externes active la connectivité Skype et les communications avec les autres organisations qui utilisent Skype Entreprise.
  
Pour plus d’informations sur l’administration de Skype Entreprise Online, voir :
  
- [Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise externes](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Que faire si vous ne pouvez pas par messagerie instantanée Skype pour les contacts externes Skype ou de l’entreprise ?](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Ajouter un contact dans Skype pour les entreprises](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Déploiement de connectivité Skype pour Skype pour Business Server

Skype pour Business Server utilise l’architecture de l’accès fédération pour prendre en charge la connectivité avec Skype. Cette connectivité permet aux utilisateurs de Skype Entreprise Server d’ajouter Skype. Les clients de Skype peuvent également ajouter des utilisateurs Skype Entreprise dans leurs listes de contacts. Selon les stratégies sont définies dans Skype pour Business Server, les utilisateurs seront en mesure de communiquer à l’aide de la messagerie instantanée, voir la présence de l’autre et effectuer des appels audio et vidéos. La connectivité Skype est également une fonctionnalité de Skype Entreprise Online, et peut être activée pour Skype Entreprise Online à partir du centre d’administration Skype Entreprise dans le portail Office 365.
  
> [!NOTE]
> Si Skype Entreprise Server est configuré pour se connecter à Windows Messenger via la connectivité PIC (Public IM Connectivity), votre déploiement est déjà configuré pour la connectivité Skype. Vous pouvez éventuellement renommer votre entrée Messenger PIC existante pour utiliser Skype.  
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server"></a>Accès à la Skype pour site mise en service Business Server public IM connectivity de Skype pour Business Server

Ce processus d’approvisionnement peut nécessiter jusqu’à trente jours mais peut être achevé en quelques jours selon le volume de demandes. Nous vous recommandons de commencer par commencer ce processus avant d’effectuer les étapes restantes de ce document. Une fois le processus d’approvisionnement Skype terminé pour votre compte, ce dernier est activé et vos utilisateurs éligibles sont activés pour la connectivité de messagerie instantanée publique.  
  
Pour approvisionner la connectivité Skype, vous avez besoin des informations suivantes :
  
- Numéro de contrat Microsoft
    
- Nom de domaine complet (FQDN) du service Edge d’accès
    
- Domaine(s) SIP (Session Initiation Protocol)
    
- Noms complets (FQDN) supplémentaires éventuels du service Edge d’accès
    
- Coordonnées
    
Pour lancer le processus d’approvisionnement pour la connectivité Skype :
  
1. Se connecter au site Web, https://pic.lync.com, à l’aide de votre Microsoft Windows Live ID.
    
2. Sélectionnez le type de contrat de licence Microsoft.
    
3. Activez la case à cocher indiquant que vous avez lu et accepté les droits d’utilisation du produit pour Skype Entreprise Server.
    
4. Dans la page Émettre une demande d’approvisionnement, cliquez sur le lien approprié pour émettre une demande d’approvisionnement :
    
5. Dans la page Indiquer les informations d’approvisionnement, entrez le nom complet du service Edge d’accès. Par exemple, sip.contoso.com.
    
    > [!IMPORTANT]
    > Après le 1er juillet 2017, les clients devront également disposer du déploiement de l’enregistrement SRV DSN pour la fédération afin d’assurer le fonctionnement de la connectivité de la messagerie instantanée publique.  
  
6. Entrez au moins un nom de domaine SIP, puis cliquez sur Ajouter.
    
    > [!NOTE]
    > Au moins un serveur Edge d’accès est requis pour le processus de mise en service. Alors qu’un nom de domaine complet Edge d’accès peut prendre en charge plusieurs domaines SIP, un domaine SIP ne peut être représenté par plusieurs noms de domaine complets Edge d’accès. Le domaine SIP et le serveur Edge d’accès doivent être actifs, fonctionnels et accessibles sur le réseau.              
  
7. Dans la liste des fournisseurs de service de messagerie instantanée publique, sélectionnez Skype, cliquez sur Suivant pour ajouter des coordonnées, puis envoyez de nouveau la demande d’approvisionnement.
    
Une fois la demande d’approvisionnement envoyée, l’activation du compte et des utilisateurs pour la connectivité Skype peut prendre jusqu’à 30 jours voire seulement quelques jours selon la file d’attente.
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la fédération et de la connectivité PIC (Public IM Connectivity)

Une fois la demande d’approvisionnement transmise, vous pouvez vous concentrer sur l’environnement Skype Entreprise Server et les tâches d’administration nécessaires à la configuration de la connectivité Skype. Cette section suppose que l’administrateur a déployé Skype Entreprise Server et configuré l’accès externe, appelé serveurs Edge.  
  
Trois étapes sont nécessaires pour activer la fédération et PIC :
  
1. Configurer la fédération et PIC
    
2. Configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés
    
3. Configurer le paramètre de fournisseur PIC Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurer la fédération et la connectivité PIC

La fédération est requise pour permettre aux utilisateurs Skype de communiquer avec les utilisateurs Skype Entreprise dans votre organisation. La connectivité PIC (Public IM Connectivity) est une classe de fédération. Elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise de communiquer avec les utilisateurs Skype. La fédération et la connectivité PIC sont configurées à l’aide du panneau de configuration Skype Entreprise Server.
  
> [!NOTE]
> La fédération PIC n’est plus prise en charge par Live Communication Server 2005 SP1 ni par Office Communications Server 2007. Les plateformes prises en charge pour la fédération PIC incluent Skype pour Business Server, Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2. 
  
La fédération est requise pour permettre aux utilisateurs Skype de communiquer avec les utilisateurs Skype Entreprise dans votre organisation. La connectivité PIC (Public IM Connectivity) est une classe de fédération. Elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise de communiquer avec les utilisateurs Skype. La fédération et la connectivité PIC sont configurées à l’aide de la boîte de dialogue Configuration du serveur Edge du panneau de configuration Skype Entreprise Server, comme le montre la figure.
  
![Définir le nouveau pool Edge](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Les attributs EnableSkypeIdRouting et EnableSkypeDirectorySearch doivent être définis sur True dans les paramètres du fournisseur public (voir les instructions plus loin) pour que la recherche fonctionne. 
  
Cette procédure termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous pouvez à présent utiliser la connectivité Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide du panneau de configuration Skype Entreprise Server, l’administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler la possibilité pour les utilisateurs Skype de collaborer avec les utilisateurs Skype Entreprise Server internes.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurer le paramètre de fournisseur de PIC de Skype

À l’aide de Skype Entreprise Server Management Shell, l’administrateur doit configurer la stratégie de client Skype Entreprise pour afficher Skype comme fournisseur PIC supplémentaire.  
  
> [!NOTE]
> Les utilisateurs des fournisseurs de services Instant Messaging connectivité PIC (Public) ne peuvent pas participer à par messagerie instantanée ou des conférences dans votre organisation jusqu'à ce que vous configurez également au moins une stratégie (étape 2, plus haut dans cette procédure) pour prendre en charge la connectivité PIC. 
  
Pour les nouvelles installations, vous pouvez configurer la connectivité Skype en activant un fournisseur public Skype à l’aide du panneau de configuration Skype Entreprise Server, comme illustré.
  
![Fournisseurs fédérés SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Pour configurer la connectivité Skype lors de la mise à niveau vers Skype Entreprise Server, vous devez supprimer puis rajouter le fournisseur public Skype existant. 
  
Vous pouvez également configurer la connectivité Skype à l’aide uniquement de PowerShell. Pour configurer la connectivité Skype à l’aide de PowerShell :
  
1. À partir d’un serveur frontal Skype Entreprise Server, ouvrez Skype Entreprise Server Management Shell.
    
2. Exécutez les deux commandes suivantes :
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si vous ne disposez pas encore d’un fournisseur PIC dans votre environnement et que vous créez un nouvel environnement PIC, vous n’avez pas besoin d’exécuter l’applet de commande Remove-CsPublicProvider.  
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    À quoi servent les paramètres les moins évidents ?
    
   - ProxyFqdn : emplacement du serveur Edge de fédération Skype (détenu/géré par Microsoft)
    
   - IconURL : icône utilisé par Lync &amp; Skype pour client d’entreprise identifier les contacts Skype
    
   - NameDecorationRoutingDomain et NameDecorationExcludedDomainList : le paramétrage de ces permet aux utilisateurs d’entrer MSAs des utilisateurs Skype sans avoir besoin de savoir à propos de « décoration « domaines non Microsoft « msn.com ». Cela évite d’avoir à taper « @msn.com utilisateur (contoso.com) » pour tous les domaines qui ne sont pas dans le ExcludedDomainList. Le client Skype Entreprise formate automatiquement le compte Microsoft si le domaine ne figure PAS dans la liste Exclus. Nous avons ajouté les domaines Account Microsoft les plus courants à la liste d’exclusion.
    
     > [!NOTE]
     > Il est nécessaire de supprimer le fournisseur public puis de le rajouter en cas de nouvelles modifications. Aucune modification sur place n’est admise. 
  
     > [!NOTE]
     > Ajouté dans Lync Server 2013 CU5 &amp; client de bureau Lync dans Office 2013 SP1, NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorer la situation où Ajout de contacts Skype nécessaires pour les utilisateurs de Lync » décorent « domaines non Microsoft identifier et les acheminer vers Skype (le format de : user(contoso.com)@msn.com). Ces nouveaux paramètres permettra la mise en forme automatique de l’utilisateur de l’adresse de l’entrer dans la boîte de dialogue « Ajouter le contact Skype » avec le NameDecorationRoutingDomain (qui doit être définie sur msn.com) si elle ne contient-elle pas les domaines de la (NameDecorationExcludedDomainList Nous actuellement pouvons prennent en charge msn.com, live.com, Hotmail.com, outlook.com). 
  
3. À partir d’un client Skype Entreprise, les utilisateurs peuvent maintenant rechercher et ajouter un utilisateur Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matrice clients et interopérabilité

Le tableau ci-dessous décrit l’état d’interopérabilité entre la dernière version de Skype et la dernière version de Skype Entreprise.
  

|**Clients Skype**|**Ajouter des contacts, messagerie instantanée, présence, son et appels vidéo**|**Commentaire**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |version 7.6 ou supérieure, Windows XP et version supérieure  <br/> |**Nouveau**: prise en charge ajoutée pour le client Windows Skype en cours d’exécution sur Windows XP et Windows Vista **(nécessite la dernière version du client 7.26 ou version ultérieure)** <br/> |
|Skype Mobile - Téléphone Android et tablette   <br/> |version 6.19 ou supérieure, sur Android OS version 4.0.3 ou supérieure  <br/> |Les périphériques dont la configuration est faible peuvent ne pas prendre en charge les appels vidéo  <br/> |
|Skype Mobile - iOS  <br/> |version 6.11 ou supérieure, sur iOS 7 ou version supérieure  <br/> |iPhone 4 et versions inférieures, iPod 4ème génération et versions inférieures, iPad 1ère génération non pris en charge  <br/> |
|Skype Mac  <br/> |version 7.19 ou supérieure, sur Mac OS X 10.9 (Mavericks) ou version supérieure  <br/> |Nécessite Mac OS X 10.9 ou version supérieure  <br/> |
|Skype Universal Windows App (Windows 10), bureau et mobile  <br/> |Windows 10 (mise à jour Redstone 1 ou version supérieure)  <br/> |L’application universelle Windows fera l’objet d’une mise à jour à l’automne 2016 qui lui apportera la prise en charge de l’interopérabilité  <br/> |
   
Le tableau ci-dessous décrit l’état d’interopérabilité entre la dernière version de Skype Entreprise et la dernière version de Skype.  
  
|**Client**|**Recherche dans l’annuaire Skype et ajout de contacts**|**Skype A/V, interopérabilité avec la messagerie instantanée**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui   <br/> |Oui   <br/> |
|Skype Entreprise sur Mac  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2013  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Web App - en ligne et sur site  <br/> |N/A   <br/> |N/A   <br/> |
|Lync Mobile - Windows Phone  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Mobile - Android  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Mobile - iOS  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Room System  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Modern App (Windows 8.1)  <br/> |Oui  <br/> |Oui   <br/> |
|Lync Mac 2011  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2010  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Phone Edition  <br/> |N/A   <br/> |N/A   <br/> |
|Lync Attendant  <br/> |N/A  <br/> |N/A  <br/> |
   

