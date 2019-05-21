---
title: Installation de Skype Entreprise Server sur des serveurs de la topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Résumé: Découvrez comment installer les composants système de Skype entreprise Server sur chaque serveur dans la topologie. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: 33775765f2ae677dd48e9cc581235df275de98d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306618"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installation de Skype Entreprise Server sur des serveurs de la topologie
 
**Résumé:** Découvrez comment installer les composants système de Skype entreprise Server sur chaque serveur dans la topologie. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Lorsque la topologie est chargée dans le magasin de gestion central et qu’Active Directory connaît les serveurs qui utiliseront les rôles, vous devez installer le système Skype entreprise Server sur chacun des serveurs de la topologie. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5 comme indiqué sur le diagramme. L’installation du système Skype entreprise Server est l’étape 7 sur 8.
  
![Schéma de vue d’ensemble.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installer le système Skype entreprise Server

Une fois que vous avez publié une topologie, vous pouvez installer les composants Skype entreprise Server sur chaque serveur dans la topologie. Cette section vous guide tout au long de l’installation de Skype entreprise Server et de la configuration des rôles de serveur pour le pool frontal et des rôles serveur colocalisés avec les serveurs frontaux. Pour installer et configurer les rôles de serveurs, exécutez l’Assistant Déploiement de Skype entreprise Server sur chaque ordinateur sur lequel vous installez un rôle de serveur. Faites appel à l’Assistant Déploiement pour exécuter les quatre étapes du déploiement que sont l’installation du magasin de configurations local, l’installation des serveurs frontaux, la configuration des certificats et le démarrage des services.
  
> [!IMPORTANT]
> Vous devez utiliser le générateur de topologie pour achever et publier la topologie avant de pouvoir installer Skype entreprise Server sur des serveurs. 
  
> [!NOTE]
> Vous devez exécuter cette procédure pour tous les serveurs de la topologie. 
  
> [!CAUTION]
> Dès lors que vous avez installé Skype entreprise Server sur un serveur frontal, la première fois que vous démarrez des services, vous devez vous assurer que le service de pare-feu Windows s’exécute sur le serveur. 
  
> [!CAUTION]
> Avant de procéder à cette procédure, vérifiez que vous êtes connecté au serveur à l’aide d’un compte d’utilisateur de domaine qui est à la fois un administrateur local et un membre du groupe RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si vous n’avez pas encore exécuté le programme d’installation de Skype entreprise Server sur ce serveur, vous serez invité à entrer un lecteur et un chemin d’accès pour l’installation. Vous pouvez effectuer cette installation sur une unité autre que l’unité système, si votre organisation l’exige ou si vous rencontrez des problèmes d’espace. Vous pouvez modifier le chemin d’accès d’installation pour les fichiers Skype entreprise Server dans la boîte de dialogue **d’installation** avec un nouveau lecteur disponible. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Skype entreprise Server s’y déploiera également.
  
> [!IMPORTANT]
> Avant de commencer l’installation, assurez-vous que Windows Server est à jour à l’aide de Windows Update. 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installer le système Skype entreprise Server

1. Insérez le CD d’installation de Skype entreprise Server. Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous voulez l’installer. Cliquez sur **Oui.**
    
3. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. 
    
4. La configuration intelligente est une fonctionnalité de Skype entreprise Server sur laquelle vous pouvez vous connecter à Internet pour rechercher les mises à jour de Microsoft Update (MU) pendant le processus d’installation, comme indiqué dans l’illustration. Cela permet une meilleure expérience en vous assurant de disposer des dernières mises à jour pour le produit. Cliquez sur **Installer** pour commencer l’installation.
    
    > [!NOTE]
    > De nombreuses organisations disposent de Windows Server Update Services (WSUS) déployé dans leurs environnements d’entreprise. WSUS permet aux administrateurs de gérer entièrement la distribution des mises à jour publiées via Microsoft Update sur les ordinateurs de leur réseau. Dans le cadre de la mise à jour cumulative 1, la mise à jour de Skype entreprise Server a introduit la prise en charge de l’installation intelligente pour fonctionner avec WSUS. Les clients ayant recours au service WSUS qui déploient Skype entreprise Server pour la première fois ou à la mise à niveau à partir de l’environnement Lync Server 2013 à l’aide de la fonctionnalité de mise à niveau sur place entraînent la lecture de la mise à jour de Skype pour Windows à partir de WSUS et non vers les mises à jour. à partir de MU. Les clients qui souhaitent utiliser Smart Setup doivent exécuter les SmartSetupWithWSUS.psq sur toutes les machines avant d’exécuter Setup.exe. 
  
     ![Capture d’écran de la configuration intelligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Dans la page de l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.
    
6. Lorsque vous avez terminé, suivez les procédures décrites dans les procédures suivantes, puis cliquez sur **quitter** pour fermer l’Assistant déploiement. Répétez les procédures pour chaque serveur frontal du pool.
    
### <a name="step-1-install-local-configuration-store"></a>Étape 1 : Installer le magasin de configurations local

1. Passez en revue les prérequis, puis cliquez sur **Exécuter** en regard de l’**Étape 1 : Installer le magasin de configurations local**.
    
    > [!NOTE]
    > Il s’agit d’une copie en lecture seule du magasin central de gestion. Dans un déploiement Standard Edition, le magasin central de gestion est créé en utilisant une copie locale de SQL Server Express Edition sur le serveur frontal. Cela se produit lorsque vous exécutez la procédure Préparer d’abord le serveur Standard Edition Server. Dans un déploiement Enterprise Edition, le magasin central de gestion est créé lorsque vous publiez la topologie qui comprend un pool frontal Enterprise Edition. 
  
2. Dans la page **Installer le magasin de configurations local**, assurez-vous que l’option **Récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.
    
    SQL Server Express Edition est installé sur le serveur local. SQL Server Express Edition est nécessaire pour le magasin local de configurations.
    
3. Une fois l’installation de la configuration du serveur local terminée, cliquez sur **Terminer**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Étape 2: configurer ou supprimer les composants de Skype entreprise Server

1. Passez en revue la configuration requise, puis cliquez sur **exécuter** à côté de l' **étape 2: configurer ou supprimer les composants Skype entreprise Server**.
    
2. Sur la page **configurer les composants du serveur Skype entreprise** , cliquez sur **suivant** pour configurer les composants comme définis dans votre topologie publiée.
    
3. La page **Exécution des commandes** affiche un résumé des commandes et les informations relatives à la progression de l’installation. Lorsque vous avez effectué cette opération, vous pouvez utiliser la liste pour sélectionner un journal à afficher, puis cliquez sur **afficher le journal**.
    
4. Lorsque l’installation des composants Skype entreprise Server est terminée et que vous avez examiné les journaux le cas échéant, cliquez sur **Terminer** pour achever cette étape de l’installation.
    
    > [!NOTE]
    > Redémarrez le serveur si vous êtes invité à le faire (ce qui peut arriver si vous devez installer l’Expérience Bureau Windows). Lorsque l’ordinateur est restauré et en cours d’exécution, vous devez l’exécuter (étape 2: configurer ou supprimer les composants Skype entreprise Server). 
  
    > [!NOTE]
    > Si le programme d’installation trouve des conditions préalables qui n’ont pas été respectées, vous recevez une notification indiquant une condition préalable non satisfaite, comme le montre la figure. Répondez à la configuration requise requise, puis recommencez (étape 2: configurer ou supprimer les composants Skype entreprise Server). 
  
     ![Condition préalable requise.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vérifiez que les deux premières étapes se sont déroulées comme prévu. Confirmez la présence d’une coche verte avec le mot **Terminé**, comme indiqué dans la figure.
    
     ![Les deux premières étapes de l’installation des composants sont terminées.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Exécutez de nouveau **Windows Update** pour vérifier s’il existe des mises à jour après l’installation des composants Skype entreprise Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Étape 3 : Demande, installation ou affectation des certificats

1. Passez en revue les prérequis, puis cliquez sur **Exécuter** en regard de l’**Étape 3 : Demander, installer ou attribuer des certificats**.
    
    > [!NOTE]
    > Skype entreprise Server prend en charge la suite SHA-2 (SHA-2 utilise les longueurs synthétiques de 224, 256, 384 ou 512) des algorithmes de hachage et de signature de condensé pour les connexions provenant de clients exécutant Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Systèmes d’exploitation serveur 2012 ou Windows Server 2008 R2. Pour permettre la prise en charge de l’accès externe via la suite SHA-2, le certificat externe est émis par une autorité de certification publique pouvant également émettre un certificat avec le même hachage de longueur en bits. 
  
    > [!IMPORTANT]
    > La sélection de l’algorithme de hachage et de signature dépend des clients et serveurs qui utiliseront le certificat, et des autres ordinateurs et appareils avec lesquels les clients et serveurs communiqueront, lesquels doivent également savoir comment utiliser les algorithmes définis dans le certificat. Pour plus d’informations sur les longueurs de condensé prises en charge dans le système d’exploitation et dans certaines applications clientes, voir [blog PKI Windows-algorithme SHA2 et Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Chaque serveur frontal ou Standard Edition nécessite jusqu’à quatre certificats : le certificat oAuthTokenIssuer, un certificat par défaut, un certificat interne web et un certificat externe web. Cependant, vous pouvez demander et attribuer un certificat par défaut unique contenant les entrées d’un autre nom du sujet appropriées ainsi que le certificat oAuthTokenIssuer. Pour plus d’informations sur les exigences relatives aux certificats, voir [Configuration requise pour Skype entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > La procédure suivante décrit la configuration des certificats à partir d’une autorité de certification interne basée sur les services de certificats Active Directory. 
  
2. Dans la page **Assistant Certificat**, cliquez sur **Demander**.
    
3. Dans la page **Demande de certificat**, fournissez les données requises, notamment en sélectionnant le domaine SIP, puis cliquez sur **Suivant**.
    
4. Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification publique ou interne à votre entreprise. Vous devrez ensuite importer la réponse de certificat et lui attribuer le rôle de certificat approprié.
    
5. Dans la page **choisir une autorité** de certification, sélectionnez l’option **Sélectionner une autorité de certification dans la liste qui a été détectée dans votre environnement** , puis sélectionnez une autorité de certification connue (par enregistrement dans les services de domaine Active Directory) dans la liste. Vous pouvez aussi sélectionner l’option **Spécifier une autre autorité de certification**, entrer le nom d’une autre autorité de certification dans la zone, puis cliquer sur **Suivant**.
    
6. Dans la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur de l’autorité de certification dispose des informations requises et peut vous assister pour cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.
    
7. Dans la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur web par défaut, cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification. 
  
8. Dans la page **Nom et paramètres de sécurité**, spécifiez un **Nom convivial**. En utilisant un nom convivial, vous pouvez rapidement identifier le certificat et son utilisation. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé ou acceptez la valeur par défaut de 2 048 bits. Activez la **case à cocher marquer la clé privée du certificat comme étant** exportable si vous déterminez que le certificat et la clé privée doivent être déplacés ou copiés vers d’autres systèmes, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > La configuration minimale requise pour Skype entreprise Server est requise pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool. 
  
9. Dans la page **Informations relatives à l’organisation**, entrez éventuellement des informations sur l’organisation, puis cliquez sur **Suivant**.
    
10. Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.
    
11. Dans la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.
    
12. Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.
    
13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, dont ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.
    
14. Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.
    
15. Dans la page **Exécution de commandes**, cliquez sur **Suivant**.
    
16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. S’il est signalé comme ayant été émis et installé, mais qu’il n’est pas valide, assurez-vous que le certificat racine de l’autorité de certification du serveur a été installé. Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. Par défaut, la case à cocher **affecter le certificat aux utilisations du certificat Skype entreprise Server** est activée. If you want to manually assign the certificate, clear the check box, and then click **Finish**.
    
17. Si vous désactivez la case à cocher **affecter le certificat aux utilisations du certificat Skype entreprise Server** sur la page précédente, vous serez invité sur la page **affectation de certificat** . Click **Next**.
    
18. Dans la page **Magasin de certificats**, sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat**, puis sur **Suivant** pour continuer.
    
    > [!NOTE]
    > Si la page **État de la demande de certificat en ligne** a signalé un problème de certificat, par exemple si le certificat n’est pas valide, affichez le certificat réel pour résoudre ce problème plus facilement. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.
  
19. Dans la page **Résumé de l’attribution du certificat**, passez en revue les informations présentées pour vérifier qu’il s’agit bien du certificat à attribuer, puis cliquez sur **Suivant**.
    
20. Dans la page **Exécution de commandes**, passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez consulter le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer**.
    
21. Dans la page **Assistant Certificat**, confirmez que tous les services sont marqués d’une coche verte pour indiquer qu’ils ont tous reçu un certificat, y compris OAuthTokenIssuer, comme le montre la figure, puis cliquez sur **Fermer**.
    
     ![Certificats installés et affectés correctement.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si vous effectuez l’installation dans un environnement de laboratoire et venez de mettre en place l’autorité de certification en utilisant les services de certificat Active Directory, vous devrez redémarrer le serveur exécutant les services de certificats et également le serveur frontal avant que l’affectation de certificat s’effectue avec succès. 
  
    > [!TIP]
    >  Pour plus d’informations sur les certificats dans les services de certificats Active Directory (AD FS), voir [services de certificats Active Directory](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Étape 4 : Démarrer les services

1. Passez en revue les prérequis de l’**Étape 4 : Démarrer les services**.
    
2. If this is an Enterprise Edition Front End pool with at least three servers, Windows Fabric is used, and you must use the **Start-CsPool** cmdlet. S’il s’agit d’un serveur unique, qui est toujours le cas avec l’édition standard, vous pouvez utiliser l’applet de passe **Start-CsWindowsService** . Dans cet exemple, nous utilisons Enterprise Edition avec trois serveurs frontaux dans la liste de ressources partagées, ouvrez **Skype entreprise Server Management Shell** , puis exécutez l’applet de suspension **Start-CsPool** , comme illustré dans l’illustration. For all other roles, including Standard Edition server, you must use **Start-CsWindowsService**. To deploy roles other than the Front End role, see documentation for those particular roles.
    
     ![Démarrez les services Skype Entreprise.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Dans la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > Pour vérifier que les services ont bien démarré, nous vous recommandons d’utiliser la commande de démarrage des services sur le serveur. Cependant, il est possible qu’elle n’indique pas l’état réel du service. Nous vous recommandons de suivre l’étape **Statut du service (facultatif)** pour ouvrir la console MMC (Microsoft Management Console) et confirmer que les services ont correctement démarré, comme indiqué dans la figure. Si un service Skype entreprise Server n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la console MMC, puis cliquer sur **Démarrer**. 
  
     ![Vérifiez que les services ont démarré.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

