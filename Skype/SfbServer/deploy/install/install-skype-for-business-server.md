---
title: Installation de Skype Entreprise Server 2015 sur des serveurs de la topologie
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Résumé : Comment installer le Skype pour les composants de système d’entreprise serveur 2015 sur chaque serveur dans la topologie. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6d395ff382ae27e47b95d63b01266694108d22cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-skype-for-business-server-2015-on-servers-in-the-topology"></a>Installation de Skype Entreprise Server 2015 sur des serveurs de la topologie
 
**Résumé :** Découvrez comment installer le Skype pour les composants de système d’entreprise serveur 2015 sur chaque serveur dans la topologie. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Une fois la topologie est chargée dans le magasin Central de gestion et d’Active Directory sait quels serveurs effectuera les rôles, vous devez installer le Skype pour système Business Server sur chacun des serveurs dans la topologie. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5 comme indiqué sur le diagramme. Installer le Skype pour système de serveur d’entreprise est l’étape 7 de 8.
  
![Schéma de vue d’ensemble.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installer Skype pour système de serveur d’entreprise

Une fois que vous avez publié une topologie, vous pouvez installer le Skype pour les composants serveur de l’entreprise sur chaque serveur dans la topologie. Cette section vous guide à travers l’installation Skype pour Business Server et configurez les rôles de serveur pour le pool de Front-End et de tous les rôles de serveur sont colocalisés avec les serveurs frontaux. Pour installer et configurer des rôles de serveur, vous exécutez la Skype pour l’Assistant de déploiement Business Server sur chaque ordinateur sur lequel vous installez un rôle de serveur. Faites appel à l’Assistant Déploiement pour exécuter les quatre étapes du déploiement que sont l’installation du magasin de configurations local, l’installation des serveurs frontaux, la configuration des certificats et le démarrage des services.
  
> [!IMPORTANT]
> Vous devez utiliser le Générateur de topologies pour terminer et publier la topologie avant de pouvoir installer Skype pour Business Server sur les serveurs. 
  
> [!NOTE]
> Vous devez exécuter cette procédure pour tous les serveurs de la topologie. 
  
> [!CAUTION]
> Après avoir installé Skype pour Business Server sur un serveur frontal, la première fois que vous démarrez les services, vous devez vous assurer que le Service de pare-feu Windows est en cours d’exécution sur le serveur. 
  
> [!CAUTION]
> Avant de suivre ces étapes, assurez-vous que vous êtes connecté au serveur avec un compte d’utilisateur de domaine qui est un administrateur local et membre du groupe RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si vous n’avez pas exécuté Skype pour le programme d’installation de Business Server sur ce serveur avant, vous serez invité pour un lecteur et un chemin d’accès de l’installation. Vous pouvez effectuer cette installation sur une unité autre que l’unité système, si votre organisation l’exige ou si vous rencontrez des problèmes d’espace. Vous pouvez modifier le chemin d’installation pour le Skype pour les fichiers de serveur d’entreprise dans la boîte de dialogue **programme d’installation** sur un lecteur disponible. Si vous installez les fichiers d’installation sur ce chemin d’accès, y compris les OCSCore.msi, le reste de la Skype pour les fichiers de serveur d’entreprise déploiera il ainsi.
  
> [!IMPORTANT]
> Avant de commencer l’installation, assurez-vous que le serveur Windows est à jour à l’aide de Windows Update. 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installer Skype pour système de serveur d’entreprise

1. Insérez le Skype pour le support d’installation Business Server 2015. Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous voulez l’installer. Cliquez sur **Oui.**
    
3. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. 
    
4. Le programme d’installation Smart est une fonctionnalité de Skype pour 2015 de serveur d’entreprise où vous pouvez vous connecter à Internet pour rechercher des mises à jour à partir de Microsoft Update (MU) pendant le processus d’installation, comme indiqué dans la figure. Cela permet une meilleure expérience en vous assurant de disposer des dernières mises à jour pour le produit. Cliquez sur **Installer** pour commencer l’installation.
    
    > [!NOTE]
    > De nombreuses organisations disposent de Windows Server Update Services (WSUS) déployé dans leurs environnements d’entreprise. WSUS permet aux administrateurs de gérer entièrement la distribution des mises à jour publiées via Microsoft Update sur les ordinateurs de leur réseau. Dans le cadre de la mise à jour Cumulative 1 Skype pour Business Server introduit la prise en charge de l’installation Smart fonctionnent avec WSUS. Les clients avec WSUS déploiement Skype pour Business Server pour la première fois ou mise à niveau de l’environnement de Lync Server 2013 à l’aide de la fonctionnalité de mise à niveau sur Place ont le programme d’installation Active l’extraction des mises à jour Skype pour Windows à partir de WSUS et non de l’extraction des mises à jour à partir de MU. Les clients qui souhaitent utiliser Smart Setup doivent exécuter les SmartSetupWithWSUS.psq sur toutes les machines avant d’exécuter Setup.exe. 
  
     ![Capture d’écran de la configuration intelligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Sur la page de l’Assistant déploiement, cliquez sur **installation ou mise à jour des Skype pour système de serveur d’entreprise**.
    
6. Effectuer les procédures décrites dans les procédures suivantes, lorsque vous avez terminé les, cliquez sur **Quitter** pour fermer l’Assistant de déploiement. Répétez les procédures pour chaque serveur frontal du pool.
    
### <a name="step-1-install-local-configuration-store"></a>Étape 1 : Installer le magasin de configurations local

1. Passez en revue les prérequis, puis cliquez sur **Exécuter** en regard de l’**Étape 1 : Installer le magasin de configurations local**.
    
    > [!NOTE]
    > Il s’agit d’une copie en lecture seule du magasin central de gestion. Dans un déploiement Standard Edition, le magasin central de gestion est créé en utilisant une copie locale de SQL Server Express Edition sur le serveur frontal. Cela se produit lorsque vous exécutez la procédure Préparer d’abord le serveur Standard Edition Server. Dans un déploiement Enterprise Edition, le magasin central de gestion est créé lorsque vous publiez la topologie qui comprend un pool frontal Enterprise Edition. 
  
2. Dans la page **Installer le magasin de configurations local**, assurez-vous que l’option **Récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.
    
    SQL Server Express Edition est installé sur le serveur local. SQL Server Express Edition est nécessaire pour le magasin local de configurations.
    
3. Une fois l’installation de la configuration du serveur local terminée, cliquez sur **Terminer**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Étape 2 : Installation ou supprimer Skype pour les composants serveur de l’entreprise

1. Passez en revue les conditions requises et puis cliquez sur **exécuter** ensuite **étape 2 : installation ou suppression de Skype pour les composants du serveur Business**.
    
2. Dans la page **Définir Skype pour les composants de serveur d’entreprise** , cliquez sur **suivant** pour configurer les composants, tels que définis dans votre topologie publiée.
    
3. La page **Exécution des commandes** affiche un résumé des commandes et les informations relatives à la progression de l’installation. Lorsqu’il est terminé, vous pouvez utiliser la liste pour sélectionner un journal pour afficher et puis cliquez sur **Afficher le journal**.
    
4. Skype pour l’installation des composants serveur de l’entreprise est effectuée et que vous avez examiné les journaux si nécessaire, cliquez sur **Terminer** pour terminer cette étape de l’installation.
    
    > [!NOTE]
    > Redémarrez le serveur si vous êtes invité à le faire (ce qui peut arriver si vous devez installer l’Expérience Bureau Windows). Lorsque l’ordinateur est de retour en cours d’exécution, vous devez exécuter ce (étape 2 : installation ou suppression de Skype pour les composants du serveur Business) procédure à nouveau. 
  
    > [!NOTE]
    > Si le programme d’installation trouve des conditions préalables qui n’ont pas été respectées, vous recevez une notification indiquant une condition préalable non satisfaite, comme le montre la figure. Satisfaire les prérequis et démarrez ce (étape 2 : installation ou suppression de Skype pour les composants du serveur Business) procédure à nouveau. 
  
     ![Condition préalable requise.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vérifiez que les deux premières étapes se sont déroulées comme prévu. Confirmez la présence d’une coche verte avec le mot **Terminé**, comme indiqué dans la figure.
    
     ![Les deux premières étapes de l’installation des composants sont terminées.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Exécutez **Windows Update** pour vérifier s’il existe des mises à jour après avoir installé le Skype pour les composants de serveur d’entreprise.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Étape 3 : Demande, installation ou affectation des certificats

1. Passez en revue les prérequis, puis cliquez sur **Exécuter** en regard de l’**Étape 3 : Demander, installer ou attribuer des certificats**.
    
    > [!NOTE]
    > Skype pour Business Server prend en charge la suite de SHA-2 (SHA-2 utilise digest longueurs de 224, 256, 384 ou 512 bits) digest hachage et la signature des algorithmes pour les connexions de clients exécutant les Windows 10 Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012, ou les systèmes d’exploitation Windows Server 2008 R2. Pour permettre la prise en charge de l’accès externe via la suite SHA-2, le certificat externe est émis par une autorité de certification publique pouvant également émettre un certificat avec le même hachage de longueur en bits. 
  
    > [!IMPORTANT]
    > La sélection de l’algorithme de hachage et de signature dépend des clients et serveurs qui utiliseront le certificat, et des autres ordinateurs et appareils avec lesquels les clients et serveurs communiqueront, lesquels doivent également savoir comment utiliser les algorithmes définis dans le certificat. Pour plus d’informations sur les résumés des longueurs sont pris en charge dans le système d’exploitation et des applications clientes, consultez le [blog de l’infrastructure PKI de Windows - SHA2 et Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Chaque serveur frontal ou Standard Edition nécessite jusqu’à quatre certificats : le certificat oAuthTokenIssuer, un certificat par défaut, un certificat interne web et un certificat externe web. Cependant, vous pouvez demander et attribuer un certificat par défaut unique contenant les entrées d’un autre nom du sujet appropriées ainsi que le certificat oAuthTokenIssuer. Pour plus d’informations sur la configuration requise du certificat, reportez-vous à la section [exigences environnementales pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
    
    > [!IMPORTANT]
    > La procédure suivante décrit la configuration des certificats à partir d’une autorité de certification interne basée sur les services de certificats Active Directory. 
  
2. Dans la page **Assistant Certificat**, cliquez sur **Demander**.
    
3. Dans la page **Demande de certificat**, fournissez les données requises, notamment en sélectionnant le domaine SIP, puis cliquez sur **Suivant**.
    
4. Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification publique ou interne à votre entreprise. Vous devrez ensuite importer la réponse de certificat et lui attribuer le rôle de certificat approprié.
    
5. Dans la page **Choisissez une autorité de certification (CA)** , sélectionnez l’option **Sélectionner une autorité de certification à partir de la liste détectée dans votre environnement** , puis sélectionnez un connu (par le biais d’une inscription dans les Services de domaine Active Directory) autorité de certification à partir de la liste. Vous pouvez aussi sélectionner l’option **Spécifier une autre autorité de certification**, entrer le nom d’une autre autorité de certification dans la zone, puis cliquer sur **Suivant**.
    
6. Dans la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur de l’autorité de certification dispose des informations requises et peut vous assister pour cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.
    
7. Dans la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur web par défaut, cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification. 
  
8. Dans la page **Nom et paramètres de sécurité**, spécifiez un **Nom convivial**. En utilisant un nom convivial, vous pouvez rapidement identifier le certificat et son utilisation. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé ou acceptez la valeur par défaut de 2 048 bits. Sélectionnez la **marque de la clé du certificat privée comme étant exportable** si vous déterminez que le certificat et la clé privée doit être déplacé ou copié vers d’autres systèmes, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Skype pour Business Server possède la configuration minimale requise pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool. 
  
9. Dans la page **Informations relatives à l’organisation**, entrez éventuellement des informations sur l’organisation, puis cliquez sur **Suivant**.
    
10. Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.
    
11. Dans la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.
    
12. Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.
    
13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, dont ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.
    
14. Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.
    
15. Dans la page **Exécution de commandes**, cliquez sur **Suivant**.
    
16. Dans la page **État de la demande de certificat en ligne**, passez en revue les informations affichées. Notez que le certificat a été émis et installé dans le magasin de certificats local. Si elle est déclarée avoir été publié et installé, mais il n’est pas valide, vérifiez que le certificat d’autorité de certification racine a été installé dans le magasin du serveur autorité de certification de racine approuvés. Consultez la documentation de votre autorité de certification pour savoir comment extraire le certificat d’une autorité de certification racine de confiance. Si vous devez consulter le certificat extrait, cliquez sur **Afficher les détails du certificat**. Par défaut, la case à cocher pour **affecter le certificat Skype pour les utilisations du certificat Business Server** est sélectionnée. Si vous souhaitez attribuer manuellement le certificat, désactivez la case à cocher, puis cliquez sur **Terminer**.
    
17. Si vous avez désactivé la case à cocher pour **affecter le certificat Skype pour les utilisations de certificats de serveur d’entreprise** à la page précédente, la page de **l’Attribution du certificat** s’affiche. Cliquez sur **Suivant**.
    
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
    >  Pour plus d’informations sur les certificats dans les Services de certificats Active Directory, consultez [Les Services de certificat Active Directory](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Étape 4 : Démarrer les services

1. Passez en revue les prérequis de l’**Étape 4 : Démarrer les services**.
    
2. S’il s’agit d’un pool de serveurs frontaux Enterprise Edition avec au moins trois serveurs, Windows Fabric est utilisé et vous devez utiliser l’applet de commande **Start-CsPool**. Si un seul serveur est utilisé, ce qui est toujours le cas avec l’Édition Standard, il faut utiliser l’applet de commande **Start-CsWindowsService** . Dans cet exemple, nous utilisons Enterprise Edition avec trois serveurs Front-End dans le pool, ouvrez le **Skype pour Business Server Management Shell** et exécutez l’applet de commande **Start-CsPool** , comme illustré dans la figure. Pour tous les autres rôles, y compris le serveur Standard Edition, vous devez utiliser **Start-CsWindowsService**. Pour déployer des rôles autres que le rôle frontal, consultez la documentation de ces rôles spécifiques.
    
     ![Démarrez les services Skype Entreprise.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Dans la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > Pour vérifier que les services ont bien démarré, nous vous recommandons d’utiliser la commande de démarrage des services sur le serveur. Cependant, il est possible qu’elle n’indique pas l’état réel du service. Nous vous recommandons de suivre l’étape **Statut du service (facultatif)** pour ouvrir la console MMC (Microsoft Management Console) et confirmer que les services ont correctement démarré, comme indiqué dans la figure. Si tout Skype pour le service Business Server n’a pas démarré, vous pouvez droit sur ce service dans la console MMC et puis cliquez sur **Démarrer**. 
  
     ![Vérifiez que les services ont démarré.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

