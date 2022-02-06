---
title: Déployer le portail Web d’administration de SRS v1 dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 'Le portail Web d’administration Skype Entreprise Server Skype Room Systems v1 (SRS v1, anciennement appelé Lync Room System) est un portail web que les organisations peuvent utiliser pour gérer leurs salles de conférence Skype Room Systems. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour surveiller l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.'
---

# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Déployer le portail Web d’administration de SRS v1 dans Skype Entreprise Server

Le portail Web d’administration Skype Entreprise Server Skype Room Systems v1 (SRS v1, anciennement appelé Lync Room System) est un portail web que les organisations peuvent utiliser pour gérer leurs salles de conférence Skype Room Systems. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour surveiller l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.

Pour utiliser cette fonctionnalité, le portail Web d’administration de SRS v1 doit être déployé sur chaque Skype Entreprise Server serveur frontal. Ce guide fournit des instructions aux administrateurs sur l’installation et la configuration du portail Web d’administration SRS. Il est destiné aux administrateurs qui connaissent l’administration Skype Entreprise Server et qui ont des droits d’utilisateur d’administrateur pour modifier la topologie Skype Entreprise Server’administration.

Une fois le portail Web d’administration SRS v1 déployé sur le serveur, les administrateurs peuvent vérifier l’état des appareils SRS v1 en se connectant au site à partir de leurs ordinateurs ou ordinateurs portables.

> [!IMPORTANT]
> Téléchargez [microsoft Skype Room Systems v1 Administrative Web Portal pour Skype Entreprise Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).

Dans cet article :

- [Configurer votre environnement pour le portail Web d’administration de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installer le portail Web d’administration de SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Utiliser le portail Web d’administration SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurer votre environnement pour le portail Web d’administration de SRS v1
<a name="Config_Env"> </a>

Pour utiliser le portail Web d’administration de SRS v1, vous devez installer ou configurer les conditions préalables suivantes.

> [!IMPORTANT]
> Si le serveur est configuré avec l’authentification Kerberos et NTLM, et que SRS est en cours d’exécution sur un ordinateur qui n’est pas joint au domaine, l’authentification Kerberos échoue et l’utilisateur ne voit pas l’état de SRS dans le portail d’administration. Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM ou les authentifications NTLM et TLS-DSK (sans Kerberos), ou associez l’ordinateur SRS au domaine.

1. Installez Skype Entreprise Server mises à jour cumulatives cumulatives dans la topologie Skype Entreprise Server’installation.

    Pour obtenir la mise à jour ou voir ce qui y est inclus, voir Mises à jour Skype Entreprise Server [2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

2. Créez un utilisateur Active Directory activé pour SIP.

    Le portail Web d’administration de SRS v1 utilise ces informations d’identification pour interroger des informations à partir Skype Entreprise Server. Le nom d’utilisateur dans les exemples donnés est LRSApp.

3. Créez un groupe de sécurité Active Directory nommé LRSSupportAdminGroup.

    Créez le groupe avec l’étendue de groupe comme global et type de groupe en tant que sécurité. Les utilisateurs activés pour SIP qui sont ajoutés à ce groupe sont autorisés à voir la liste des salles et à exécuter certaines commandes, telles que la collecte de journaux.

4. Créez un groupe de sécurité Active Directory nommé LRSFullAccessAdminGroup.

    Créez le groupe avec une étendue de groupe globale et un type de groupe en tant qu’utilisateurs activés security.SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration sur une seule Skype salle. Pour inclure la prise en charge de la gestion en bloc Skype salles, reportez-vous à l’étape 5.

     ![Liste des groupes d’administration avec le rôle de groupe de sécurité.](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Créez un groupe de sécurité Active Directory nommé LRSPowerUserAdminsGroup.

    Créez le groupe avec l’étendue de groupe comme global et type de groupe en tant que sécurité. Les utilisateurs activés pour SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration, y compris la gestion en bloc Skype Entreprise salles.

6. Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.

     ![Page Membres des propriétés LRSSupportAdminGroup.](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport. Ajoutez cet utilisateur à LRSSupportAdminGroup.

     ![Page Membres des propriétés LRSSupportAdminGroup.](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installez [ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installer le portail Web d’administration de SRS v1
<a name="Install_SRS"> </a>

Téléchargez [microsoft Skype Room Systems v1 Administrative Web Portal pour Skype Entreprise Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).

Pour installer le portail Web d’administration de SRS v1, utilisez les étapes suivantes.

1. Configurez le port d’application approuvé en exécutant l’cmdlet suivante dans Skype Entreprise Server Management Shell :

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Pour installer le portail Salle de réunion, téléchargez **MeetingRoomPortalInstaller.msi** puis exécutez-le en tant qu’administrateur.

3. Ouvrez le Web.config à partir de l’emplacement suivant :

    %Program Files%\Skype Entreprise Server 2015\Web Components\Salle de réunion Portal\Int\Handler\

4. Dans le fichier Web.Config, modifiez PortalUserName en nom d’utilisateur créé à l’étape 2 sous la section « Configurer votre environnement pour le portail web d’administration [de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env) » (le nom recommandé à l’étape est LRSApp) :

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Étant donné que le portail d’administration SRS v1 est une application fiable, vous n’avez pas besoin de fournir le mot de passe dans la configuration du portail. Si cet utilisateur utilise un bureau d’enregistrement différent du bureau d’enregistrement local, vous devez spécifier le bureau d’enregistrement pour celui-ci en ajoutant la ligne suivante dans Web.Config fichier :

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Si le port utilisé est autre que 5061, ajoutez la ligne suivante dans Web.Config fichier :

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Vérifier l’installation du portail Web d’administration SRS

Pour vérifier l’installation du portail Web d’administration de SRS v1, vous pouvez :

1. Sur un serveur frontal, accédez à l’URL suivante :

    \<fe-server\>https:///lrs

    Vous ne devriez voir aucune erreur, comme illustré dans l’image suivante :

     ![Écran de signature du portail d’administration Lync Room System.](../../media/LRS_AdminPortalSignIn.png)

2. Si vous ne voyez aucune erreur, essayez d’accéder à l’URL suivante à partir d’un autre ordinateur de la topologie :

    \<fe-server\>https:///lrs

    Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans « [Enregistrements DNS](/previous-versions/office/communications-server/bb663700(v=office.12)) requis pour la signature automatique du client ».

## <a name="use-the-srs-administrative-web-portal"></a>Utiliser le portail Web d’administration SRS
<a name="Use_Portal"> </a>

Après avoir déployé SRS sur le serveur, vous pouvez vérifier l’état de toutes les salles SRS en vous inscrivant dans le portail Web d’administration de SRS v1 à partir d’un navigateur.

### <a name="sign-in"></a>Se connecter

1. Accédez à l’URL suivante :

    \<fe-server\>https:///lrs

2. Entrez les informations d’identification du compte LRSSupport ou d’un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.

![Écran de signature du portail d’administration Lync Room System.](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Page récapitulatif du portail Web d’administration SRS

La page récapitulatif fournit les informations suivantes pour toutes les salles SRS déployées sur le serveur :

- **Balise** Nom personnalisé que l’administrateur donne à la salle. La balise peut être définie dans le portail en cliquant sur le nom de la salle.

- **Santé** L’état d’état de la salle, qui est dérivé de l’état d’agrégation de la salle, qui est affiché sous la section Santé de la page Salle Paramètres.

- **Réunion suivante** Date et heure de la prochaine réunion.

- **Version, fabricant, modèle SRS** Ces valeurs sont prédéfines dans SRS. Selon le fabricant, ces champs peuvent être laissés vides.

- **Dernière actualisation** Affiche la dernière fois que la page web a été actualisée.

![Affichage récapitulatif du portail d’administration Lync Room System.](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Vous ne verrez le menu Gestion en bloc que si vous faites partie du groupe de sécurité LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informations sur la salle SRS

La section Informations sur la salle du portail vous permet d’afficher et de configurer des salles SRS individuelles. Il contient quatre sections : Paramètres, Détails, Journalisation et Santé.

#### <a name="settings"></a>Paramètres

Dans la section Paramètres, vous pouvez définir le mot de passe, la balise de salle et les niveaux de volume par défaut de la salle. Si vous configurez ces paramètres, les modifications sont répliquées uniquement après le redémarrage de la console SRS. Vous ne verrez que les paramètres des mises à jour système pour les appareils SRS utilisant la version 15.12 et ultérieures.

![Salle du portail d’administration Lync Room System Paramètres.](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Détails

La section Détails fournit un résumé en lecture seule des paramètres de la salle SRS, y compris : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et étalonnage ; paramètres par défaut du haut-parleur, du micro et de la sonnerie ; version; URI SIP ; nombre d’écrans et de détails sur chaque écran ; statut et activité.

![Affichage détaillé du portail d’administration Lync Room System.](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Résolution des problèmes

La section Dépannage peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié. Vous pouvez également redémarrer la console SRS (interface utilisateur SRS) ou redémarrer l’ensemble du système. Pour collecter les journaux, fournissez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier dispose des autorisations d’écriture accordées au compte d’ordinateur SRS. Si la taille du journal est trop importante, la collecte des journaux peut prendre jusqu’à 5 minutes. L’actualisation de la page vous donne l’état le plus récent.

#### <a name="health"></a>Intégrité

La section Santé fournit une indication visuelle de l’état de la connexion Skype Entreprise Server, du périphérique audio, du périphérique vidéo, de l’état de résilience et de l’écran.

![Lync Room System Admin Portal Room Health.](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Notes supplémentaires sur le portail Web d’administration

> [!NOTE]
>  Les modifications de paramètre sont appliquées uniquement après le redémarrage du système SRS.> Si le mot de passe du compte LRSApp expire, vous ne pourrez pas voir l’état des salles. Configurez le mot de passe du compte LRSAppuser de sorte qu’il n’expire jamais, ou assurez-vous de le mettre à jour lorsqu’il est sur le point d’expirer.> Le portail web d’administration SRS est uniquement pris en charge pour les déploiements locaux.

### <a name="bulk-management"></a>Gestion en bloc

La gestion en bloc des salles SRS est une fonctionnalité conçue pour les administrateurs informatiques avancés, pour simplifier leur flux de travail et leur permettre de gagner du temps et de gérer à distance plusieurs salles en bloc.

Pour voir cette fonctionnalité, l’utilisateur doit être provisioné en tant que membre du groupe de sécurité spécial **, LRSPowerUserAdminsGroup**.

Il n’existe aucune limite au nombre de salles SRS que vous pouvez sélectionner pour la gestion en bloc. Toutefois, vous ne pouvez effectuer qu’une seule opération de gestion en bloc à la fois.

Pour effectuer une opération de gestion en bloc, sélectionnez les salles à surveiller, puis cliquez sur le menu Gestion en bloc.

### <a name="frequently-asked-questions"></a>Questions fréquemment posées

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Pourquoi ne puis-je pas me connecter au portail web d’administration ?

Lorsque vous ouvrez https://localhost/lrs, vous pouvez voir la page de connexion, mais lorsque vous tapez vos informations d’identification, vous ne pouvez pas vous y inscrire. Dans ce cas, vous devez ouvrir pour https://FQDNofFEserver/SRS vous inscrire au portail web d’administration.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir SRS v1 dans le portail web d’administration ?

- Assurez-vous que vous avez des comptes SRS dans votre déploiement et qu’ils sont créés conformément aux recommandations de déploiement du portail Web d’administration SRS. Assurez-vous que les comptes SRS sont provisionés à l’aide de Enable-CsMeetingRoom, et non de Enable-CsUser, sur le Skype Entreprise Server.

- Si vous avez créé des comptes SRS et que vous ne pouvez pas les voir dans le portail web d’administration, collectez les journaux du serveur à l’aide de l’outil de journalisation Skype Entreprise Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact de support SRS.

- Si vous avez créé des comptes SRS et que vous ne pouvez pas les voir dans le portail web d’administration, collectez les journaux clients à l’aide de Fiddler, copiez également le journal de la console à partir des outils de développement du navigateur, puis envoyez-les à votre contact de support SRS. Vous pouvez également modifier la valeur du niveau de suivi dans le Web.config pour obtenir un journal plus détaillé.

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir l’état de SRS dans le portail web d’administration ?

- Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.

- Si vous avez encore des problèmes, collectez le fichier **Trace.log** dans le système SRS à partir de D:\Tracing\LRSAdminLogs\, , puis envoyez-le à votre contact de support SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir les menus de gestion en bloc pour SRS dans le portail web d’administration ?

Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP et qu’il fait partie du groupe de sécurité LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Le portail web d’administration SRS v1 fonctionne-t-il avec Salles Microsoft Teams ?

Non.