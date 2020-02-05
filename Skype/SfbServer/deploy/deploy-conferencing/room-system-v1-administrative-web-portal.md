---
title: Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server
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
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Le portail Web d’administration de Skype entreprise Server v1 (SRS v1, auparavant appelé système de salle Lync) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de systèmes de salle Skype. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour contrôler l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Ils peuvent également collecter à distance des informations de diagnostic pour surveiller l’intégrité des salles de conférence.
ms.openlocfilehash: 558baac64bdb1e21ed710cb4dafb063ce75a62de
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768517"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server

Le portail Web d’administration de Skype entreprise Server v1 (SRS v1, auparavant appelé système de salle Lync) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de systèmes de salle Skype. Les administrateurs peuvent utiliser le portail Web d’administration de SRS v1 pour contrôler l’état de l’appareil, par exemple en surveillant les périphériques audio/vidéo. Ils peuvent également collecter à distance des informations de diagnostic pour surveiller l’intégrité des salles de conférence.

Pour utiliser cette fonctionnalité, le portail Web d’administration de SRS v1 doit être déployé sur chaque serveur frontal Skype entreprise Server. Ce guide fournit des instructions aux administrateurs sur l’installation et la configuration du portail Web d’administration SRS. Il est destiné aux administrateurs ayant connaissance de l’administration de Skype entreprise Server et disposant de droits d’administrateur pour la modification de la topologie de Skype entreprise Server.

Après le déploiement du portail Web d’administration SRS v1 sur le serveur, les administrateurs peuvent vérifier les appareils SRS v1 en se connectant au site à partir de leur ordinateur ou de leur ordinateur portable.

> [!IMPORTANT]
> Télécharger le [portail Web d’administration des systèmes de salle Skype Microsoft pour Skype entreprise Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Contenu de cette rubrique :

- [Configuration de votre environnement pour le portail Web d’administration de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installation du portail Web d’administration de SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Utilisation du portail Web d’administration de SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configuration de votre environnement pour le portail Web d’administration de SRS v1
<a name="Config_Env"> </a>

Pour utiliser le portail Web d’administration de SRS v1, vous devez remplir les conditions préalables suivantes.

> [!IMPORTANT]
> Si le serveur est configuré avec les authentifications Kerberos et NTLM, et que SRS est en cours d’exécution sur un ordinateur non associé au domaine, l’authentification Kerberos échouera et l’utilisateur ne pourra pas visualiser le statut de SRS sur le portail d’administration. Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM, ou avec les authentifications NTLM et TLS-DSK (sans Kerberos), ou associez l’ordinateur SRS au domaine.

1. Installez les mises à jour cumulatives de Skype entreprise Server dans la topologie de Skype entreprise Server.

    Pour obtenir la mise à jour ou découvrir ce qu’elle contient, voir [mises à jour de Skype entreprise Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

2. Créez un utilisateur Active Directory activé pour SIP.

    Le portail Web d’administration de SRS v1 utilise ces informations d’identification pour interroger les informations de Skype entreprise Server. Le nom d’utilisateur dans les exemples présentés est LRSApp.

3. Créez un groupe de sécurité Active Directory nommé LRSSupportAdminGroup.

    Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe seront autorisés à afficher la liste des pièces et à exécuter certaines commandes, telles que la collecte de journaux.

4. Créez un groupe de sécurité Active Directory nommé LRSFullAccessAdminGroup. 

    Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration dans une seule salle Skype. Pour inclure la prise en charge de la gestion en bloc de salles Skype, reportez-vous à l’étape 5. 

     ![Liste des groupes d’administrateurs avec rôle de groupe de sécurité](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Créez un groupe de sécurité Active Directory nommé LRSPowerUserAdminsGroup.

    Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs SIP activés qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration, y compris la gestion en bloc des salles Skype entreprise.

6. Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.

     ![Page des membres des propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport. Ajoutez cet utilisateur au groupe LRSSupportAdminGroup.

     ![Page des membres des propriétés LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installez [ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installation du portail Web d’administration de SRS v1
<a name="Install_SRS"> </a>

Télécharger le [portail Web d’administration des systèmes de salle Skype Microsoft pour Skype entreprise Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Pour installer le portail Web d’administration de SRS v1, procédez comme suit.

1. Configurez le port d’application fiable en exécutant l’applet de commande suivante dans Skype entreprise Server Management Shell :

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Pour installer le portail d’administration de salles de réunions, téléchargez **MeetingRoomPortalInstaller.msi**, puis exécutez-le en tant qu’administrateur.

3. Ouvrez le fichier Web.config à partir de l’emplacement suivant :

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. Dans le fichier Web. config, remplacez PortalUserName par le nom d’utilisateur créé à l’étape 2 de la section «[configurer votre environnement pour le portail Web d’administration SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)» (le nom recommandé dans l’étape est LRSApp) :

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Comme le portail d’administration de SRS v1 est une application approuvée, vous n’avez pas besoin d’indiquer le mot de passe dans la configuration du portail. Si cet utilisateur utilise un autre serveur d’inscriptions que le serveur d’inscriptions local, vous devez le spécifier en ajoutant la ligne suivante dans le fichier Web.Config : 

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Si le port utilisé n’est pas le port 5061, ajoutez la ligne suivante dans le fichier Web.Config : 

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Vérification du portail Web d’administration de SRS

Pour vérifier l’installation du portail Web d’administration de SRS v1, procédez comme suit :

1. Sur un serveur frontal, accédez à l’URL suivante :

    https://\<Fe-Server\>/LRS

    Aucune erreur ne doit s’afficher, comme dans l’image suivante :

     ![Écran Connexion au portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

2. Si aucune erreur ne s’affiche, essayez d’accéder à l’URL suivante à partir d’un autre ordinateur dans la topologie :

    https://\<Fe-Server\>/LRS

    Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans la section «[enregistrements DNS requis pour la connexion automatique au client](https://go.microsoft.com/fwlink/p/?LinkId=318056)».

## <a name="use-the-srs-administrative-web-portal"></a>Utilisation du portail Web d’administration de SRS
<a name="Use_Portal"> </a>

Une fois que vous avez déployé SRS sur le serveur, vous pouvez vérifier le statut de toutes les salles LRS en vous connectant au portail Web d’administration de SRS v1 à partir d’un navigateur.

### <a name="sign-in"></a>Connexion

1. Accédez à l’URL suivante :

    https://\<Fe-Server\>/LRS

2. Entrez les données d’identification du compte LRSSupport ou d’un compte ajouté au groupe de sécurité LRSSupportAdminGroup.

![Écran Connexion au portail d’administration Lync Room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Page Récapitulatif du portail Web d’administration de SRS

La page Récapitulatif fournit les informations ci-dessous pour toutes les salles SRS déployées sur le serveur :

- **Indicateur** Nom personnalisé que l’administrateur accorde à la salle. Le libellé peut être défini sur le portail en cliquant sur le nom de la salle.

- **État d’intégrité** État d’intégrité de la salle, qui est dérivée de l’état d’intégrité agrégé de la salle, qui s’affiche dans la section intégrité de la page Paramètres de la salle.

- **Réunion suivante** Date et heure de la planification de la réunion suivante.

- **Version SRS, fabricant et modèle** Ces valeurs sont prédéfinies dans SRS. Selon la marque, ces champs peuvent rester vides.

- **Dernière actualisation** Affiche la date à laquelle la page Web a été actualisée pour la dernière fois.

![Affichage de synthèse du portail d’administration Lync Room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Le menu gestion en bloc ne s’affichera que si vous faites partie du groupe de sécurité LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informations sur la salle SRS

La section Informations sur la salle du portail permet d’afficher et de configurer des salles SRS individuelles. Elle contient quatre sections : Paramètres, Détails, Journalisation et Intégrité.

#### <a name="settings"></a>Paramètres

Dans la section Paramètres, vous pouvez définir le mot de passe, le libellé de la salle et les niveaux de volume par défaut pour la salle. Si vous configurez ces paramètres, les modifications sont répliquées uniquement après le redémarrage de la console SRS. Les paramètres des mises à jour système seront visibles uniquement pour les périphériques SRS utilisant la version 15.12 ou une version ultérieure.

![Paramètre de la salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Détails

La section Détails fournit une synthèse en lecture seule des paramètres de la salle de SRS, notamment : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et calibrage ; paramètres de haut-parleur, micro et sonnerie par défaut ; version9.0.2 URI SIP ; nombre d’écrans et de détails relatifs à chaque écran ; État et activité.

![Affichage détaillé du portail d’administration Lync Room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Résolution des problèmes

La section Dépannage peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié. Vous pouvez également redémarrer la console SRS (interface utilisateur SRS) ou redémarrer tout le système. Pour collecter des journaux, fournissez un chemin d’accès à un dossier au format spécifié et assurez-vous que ce dossier accorde des autorisations en écriture au compte de l’ordinateur SRS. Si la taille du journal est trop volumineuse, la collecte peut prendre jusqu’à 5 minutes. Actualisez la page pour obtenir le dernier statut.

#### <a name="health"></a>Intégrité

La section santé fournit une indication visuelle de l’état de la connexion à Skype entreprise Server, du périphérique audio, de l’appareil vidéo, de l’état de résilience et du périphérique d’écran.

![Intégrité de la salle du portail d’administration Lync Room System](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Remarques supplémentaires concernant le portail Web d’administration

> [!NOTE]
>  Les modifications apportées aux paramètres ne s’appliquent qu’après le redémarrage du système SRS. > si le mot de passe du compte LRSApp expire, vous ne serez pas en mesure de voir l’état des salles. Configurez le mot de passe du compte LRSAppuser pour qu’il n’expire jamais, ou veillez à le mettre à jour en cas d’expiration proche. > le portail Web d’administration SRS est uniquement pris en charge pour les déploiements sur site.

### <a name="bulk-management"></a>Gestion en bloc 

La gestion en bloc des salles SRS est une fonctionnalité conçue pour les administrateurs informatiques avancés, afin de simplifier leur flux de travail, et de leur proposer un outil rapide de gestion à distance de différentes salles en bloc.

Pour afficher cette fonctionnalité, l’utilisateur doit être approvisionné en tant que membre du groupe de sécurité spécial **LRSPowerUserAdminsGroup**.  

Le nombre de salles SRS que vous pouvez sélectionner pour la gestion en bloc est illimité. Toutefois, vous pouvez réaliser une seule opération de gestion en bloc à la fois.

Pour effectuer une opération de gestion en bloc, sélectionnez les salles à surveiller et cliquez sur le menu de gestion en bloc. 

### <a name="frequently-asked-questions"></a>Forum aux questions

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Pourquoi ne puis-je pas me connecter au portail Web d’administration ?

Lorsque vous ouvrez https://localhost/lrsla page de connexion, vous pouvez voir la page de connexion, mais si vous entrez vos informations d’identification, vous ne pourrez pas vous connecter. Dans ce cas, vous devez ouvrir https://FQDNofFEserver/SRS pour vous connecter au portail Web d’administration.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir SRS v1 dans le portail Web d’administration ?

- Assurez-vous que votre déploiement comporte des comptes SRS et qu’ils ont été créés selon les recommandations de déploiement du portail Web d’administration de SRS. Assurez-vous que les comptes SRS sont approvisionnés à l’aide de Enable-CsMeetingRoom, et non d’Enable-CsUser, sur le serveur Skype entreprise.

- Si vous avez créé des comptes SRS et ne pouvez pas les afficher dans le portail Web administratif, collectez les journaux du serveur à l’aide de l’outil de journalisation de Skype entreprise Server avec le composant **MeetingPortal** sélectionné, puis envoyez-le à votre contact du support SRS.

- Si vous avez créé des comptes SRS et que vous ne les voyez pas sur le portail Web d’administration, collectez les journaux clients à l’aide de Fiddler, copiez également le journal de la console à partir des outils de développement du navigateur et envoyez-les à votre contact d’assistance pour SRS. Vous pouvez également modifier la valeur de niveau du suivi dans le fichier Web.config pour obtenir un journal plus détaillé.

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir l’état de SRS dans le portail Web d’administration ?

- Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.

- Si vous rencontrez encore des problèmes, collectez le fichier **trace. log** dans le système SRS à\, partir de D:\Tracing\LRSAdminLogs, puis envoyez-le à votre contact du support SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir les menus de gestion en bloc pour le service SRS dans le portail Web d’administration ?

Assurez-vous que le compte d’utilisateur LRSApp est compatible SIP et fait partie du groupe de sécurité LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Le portail Web d’administration de SRS v1 fonctionne-t-il avec les salles de Microsoft teams ?

Non


