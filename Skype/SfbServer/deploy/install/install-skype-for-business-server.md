---
title: Installer Skype entreprise Server sur les serveurs de la topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Résumé : Découvrez comment installer les composants système de Skype entreprise Server sur chaque serveur de la topologie. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 0fe1c7b6088732932457d25c68a8fd6476a1bfbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018245"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installer Skype entreprise Server sur les serveurs de la topologie
 
**Résumé :** Découvrez comment installer les composants du système Skype entreprise Server sur chaque serveur de la topologie. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Une fois que la topologie est chargée dans le magasin central de gestion et qu’Active Directory sait quels serveurs effectueront quels sont les rôles, vous devez installer le système Skype entreprise Server sur chacun des serveurs de la topologie. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. L’installation du système Skype entreprise Server est l’étape 7 sur 8.
  
![Diagramme de vue d’ensemble.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installer le système Skype entreprise Server

Une fois que vous avez publié une topologie, vous pouvez installer les composants Skype entreprise Server sur chaque serveur de la topologie. Cette section vous guide tout au long de l’installation de Skype entreprise Server et de la configuration des rôles serveur du pool frontal et de tous les rôles serveur colocalisés avec les serveurs frontaux. Pour installer et configurer les rôles serveur, exécutez l’Assistant Déploiement de Skype entreprise Server sur chaque ordinateur sur lequel vous installez un rôle serveur. L’Assistant déploiement vous permet d’effectuer les quatre étapes de déploiement, notamment l’installation du magasin de configurations local, l’installation des serveurs frontaux, la configuration des certificats et le démarrage des services.
  
> [!IMPORTANT]
> Vous devez utiliser le générateur de topologies pour terminer et publier la topologie avant de pouvoir installer Skype entreprise Server sur des serveurs. 
  
> [!NOTE]
> Cette procédure doit être exécutée pour tous les serveurs de la topologie. 
  
> [!CAUTION]
> Une fois que vous avez installé Skype entreprise Server sur un serveur frontal, la première fois que vous démarrez les services, vous devez vous assurer que le service pare-feu Windows est en cours d’exécution sur le serveur. 
  
> [!CAUTION]
> Avant de suivre ces étapes, vérifiez que vous êtes connecté au serveur avec un compte d’utilisateur de domaine qui est à la fois un administrateur local et un membre du groupe RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si vous n’avez pas encore exécuté le programme d’installation de Skype entreprise Server sur ce serveur, vous serez invité à indiquer un lecteur et un chemin d’accès pour l’installation. Cela permet d’installer sur un lecteur autre que le lecteur système, si votre organisation l’exige ou si vous avez des préoccupations en matière d’espace. Vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers de Skype entreprise Server dans la boîte de dialogue de **configuration** en tant que nouveau lecteur disponible. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Skype entreprise Server se déploiera également.
  
> [!IMPORTANT]
> Avant de commencer l’installation, assurez-vous que Windows Server est à jour à l’aide de Windows Update. 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installer le système Skype entreprise Server

1. Insérez le support d’installation de Skype entreprise Server. Si le programme d’installation ne commence pas automatiquement, double-cliquez sur **configuration**.
    
2. Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît et vous demande si vous souhaitez l’installer. Cliquez sur **Oui.**
    
3. Lisez attentivement le contrat de licence et, si vous l’acceptez, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. 
    
4. La configuration intelligente est une fonctionnalité de Skype entreprise Server dans laquelle vous pouvez vous connecter à Internet pour vérifier les mises à jour à partir de Microsoft Update (MU) pendant le processus d’installation, comme illustré dans la figure. Cela permet une meilleure expérience en s’assurant que vous disposez des mises à jour les plus récentes pour le produit. Cliquez sur **Installer** pour commencer l’installation.
    
    > [!NOTE]
    > De nombreuses organisations ont déployé Windows Server Update Services (WSUS) dans leur environnement d’entreprise. WSUS permet aux administrateurs de gérer entièrement la distribution des mises à jour publiées via Microsoft Update sur les ordinateurs de leur réseau. Dans le cadre de la mise à jour cumulative 1, Skype entreprise Server a introduit la prise en charge de la configuration intelligente pour qu’elle fonctionne avec WSUS. Les clients avec WSUS qui déploient Skype entreprise Server pour la première fois ou la mise à niveau à partir de l’environnement Lync Server 2013 à l’aide de la fonctionnalité de mise à niveau sur place disposeront d’une configuration intelligente extrayant les mises à jour de Skype entreprise à partir de WSUS, plutôt que d’extraire les mises à jour. à partir de MU. Les clients souhaitant utiliser le programme d’installation intelligent doivent exécuter le SmartSetupWithWSUS. de l’aide du client sur tous les ordinateurs avant d’exécuter Setup. exe. 
  
     ![Capture d’écran de la configuration intelligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Sur la page Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.
    
6. Suivez les procédures décrites dans les procédures suivantes, une fois que vous avez terminé, cliquez sur **quitter** pour fermer l’Assistant déploiement. Répétez les procédures pour chaque serveur frontal du pool.
    
### <a name="step-1-install-local-configuration-store"></a>Étape 1 : installer le magasin de configurations local

1. Examinez les éléments prérequis, puis cliquez sur **exécuter** à côté de **étape 1 : installer le magasin de configurations local**.
    
    > [!NOTE]
    > Le magasin de configurations local est une copie en lecture seule du magasin central de gestion. Dans un déploiement Standard Edition, le magasin central de gestion est créé à l’aide d’une copie locale de SQL Server Express Edition sur le serveur frontal. Cela se produit lorsque vous exécutez la procédure prepare First Standard Edition Server. Dans un déploiement Enterprise Edition, le magasin central de gestion est créé lorsque vous publiez la topologie qui comprend un pool frontal Enterprise Edition. 
  
2. Sur la page **installer le magasin de configurations local** , assurez-vous que l’option **récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **suivant**.
    
    SQL Server Express Edition est installé sur le serveur local. SQL Server Express Edition est requis pour le magasin de configurations local.
    
3. Une fois l’installation terminée, cliquez sur **Terminer**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Étape 2 : installer ou supprimer des composants Skype entreprise Server

1. Examinez les éléments prérequis, puis cliquez sur **exécuter** à côté de **étape 2 : installer ou supprimer des composants Skype entreprise Server**.
    
2. Sur la page **configurer les composants de Skype entreprise Server** , cliquez sur **suivant** pour configurer les composants comme défini dans votre topologie publiée.
    
3. La page **exécution de commandes** affiche un résumé des commandes et des informations d’installation à mesure que la configuration a lieu. Une fois cette opération terminée, vous pouvez sélectionner un journal à afficher dans la liste, puis cliquer sur **afficher le journal**.
    
4. Lorsque l’installation des composants Skype entreprise Server est terminée et que vous avez vérifié les journaux selon vos besoins, cliquez sur **Terminer** pour effectuer cette étape dans l’installation.
    
    > [!NOTE]
    > Redémarrez le serveur si vous y êtes invité (ce qui peut se produire si l’expérience de bureau Windows devait être installée). Lorsque l’ordinateur est en cours de sauvegarde et en cours d’exécution, vous devez réexécuter cette procédure (étape 2 : installer ou supprimer des composants Skype entreprise Server). 
  
    > [!NOTE]
    > Si le programme d’installation trouve des éléments prérequis qui n’ont pas été satisfaits, vous en serez averti par le message « prérequis non satisfait », comme illustré dans la figure. Répondez aux conditions préalables requises, puis démarrez cette procédure (étape 2 : installer ou supprimer des composants Skype entreprise Server). 
  
     ![Conditions préalables requises.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vérifiez que les deux premières étapes sont terminées comme prévu. Vérifiez qu’il y a une coche verte avec le mot **terminé**, comme illustré dans la figure.
    
     ![Les deux premières étapes sont effectuées à partir de l’installation des composants.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Exécutez de nouveau **Windows Update** pour vérifier s’il existe des mises à jour après avoir installé les composants de Skype entreprise Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Étape 3 : demander, installer ou assigner des certificats

1. Passez en revue les éléments prérequis, puis cliquez sur **exécuter** en regard de l' **étape 3 : demander, installer ou assigner les certificats**.
    
    > [!NOTE]
    > Skype entreprise Server inclut la prise en charge de la suite SHA-2 (SHA-2 utilise les longueurs des Digest 224, 256, 384 ou 512 bits) des algorithmes de hachage et de signature Digest pour les connexions à partir de clients exécutant Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Systèmes d’exploitation Server 2012 ou Windows Server 2008 R2. Pour prendre en charge l’accès externe à l’aide de la suite SHA-2, le certificat externe est émis par une autorité de certification publique qui peut également émettre un certificat avec le même chiffrement de longueur en bits. 
  
    > [!IMPORTANT]
    > La sélection de l’algorithme de hachage et du Digest de hachage dépend des clients et des serveurs qui utiliseront le certificat, ainsi que d’autres ordinateurs et appareils avec lesquels les clients et les serveurs communiqueront, qui doivent également savoir comment utiliser les algorithmes utilisés dans le titre. Pour plus d’informations sur les longueurs de résumé prises en charge dans le système d’exploitation et certaines applications clientes, consultez la rubrique [Windows PKI blog-SHA2 et Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Chaque serveur frontal ou édition standard requiert jusqu’à quatre certificats : le certificat oAuthTokenIssuer, un certificat par défaut, un certificat interne Web et un certificat externe Web. Toutefois, vous pouvez demander et affecter un certificat par défaut unique avec les autres entrées de nom de sujet appropriées, ainsi que le certificat oAuthTokenIssuer. Pour plus d’informations sur les certificats requis, reportez-vous à [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > La procédure suivante décrit comment configurer des certificats à partir d’une autorité de certification basée sur les services de certificats Active Directory interne. 
  
2. Dans la page **Assistant Certificat**, cliquez sur **Demander**.
    
3. Sur la page **demande de certificat** , renseignez les données appropriées, notamment en sélectionnant le domaine SIP, puis cliquez sur **suivant**.
    
4. Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification interne à votre entreprise ou publique. Vous devrez ensuite importer la réponse du certificat et lui attribuer le rôle approprié.
    
5. Sur la page **choisir une autorité** de certification, sélectionnez l’option **Sélectionner une autorité de certification dans la liste détectée dans votre environnement** , puis sélectionnez une autorité de certification connue (par le biais de l’inscription dans les services de domaine Active Directory) dans la liste. Ou sélectionnez l’option **Spécifier une autre autorité de certification**, entrez le nom d’une autre autorité de certification dans la zone, puis cliquez sur **Suivant**.
    
6. Sur la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur d’autorité de certification dispose des informations requises et peut vous aider dans cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.
    
7. Sur la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur Web par défaut, cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification. 
  
8. Dans la page **nom et paramètres de sécurité** , spécifiez un **nom convivial**. À l’aide d’un nom convivial, vous pouvez rapidement identifier le certificat et l’objectif. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé, ou acceptez la valeur par défaut de 2 048 bits. Activez la **case à cocher marquer la clé privée du certificat comme exportable** si vous déterminez que le certificat et la clé privée doivent être déplacés ou copiés sur d’autres systèmes, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Skype entreprise Server a une configuration minimale requise pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool. 
  
9. Dans la page **Informations relatives à l’entreprise**, entrez éventuellement des informations sur l’entreprise, puis cliquez sur **Suivant**.
    
10. Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.
    
11. Sur la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.
    
12. Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.
    
13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, y compris ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.
    
14. Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.
    
15. Dans la page **Exécution de commandes**, cliquez sur **Suivant**.
    
16. Dans la page **État de la demande de certificat en ligne**, passez en revue les informations affichées. Notez que le certificat a été émis et installé dans le magasin de certificats local. Si elle est signalée comme ayant été émise et installée, mais n’est pas valide, vérifiez que le certificat racine de l’autorité de certification a été installé dans le magasin d’AC racines de confiance du serveur. Consultez la documentation de votre autorité de certification pour savoir comment extraire le certificat d’une autorité de certification racine de confiance. Si vous devez consulter le certificat extrait, cliquez sur **Afficher les détails du certificat**. Par défaut, la case à cocher **affecter le certificat aux utilisations de certificat Skype entreprise Server** est activée. Si vous souhaitez attribuer manuellement le certificat, désactivez la case à cocher, puis cliquez sur **Terminer**.
    
17. Si vous avez désactivé la case à cocher **affecter le certificat aux utilisations de certificat Skype entreprise Server** sur la page précédente, la page **affectation de certificat** s’affiche. Cliquez sur **Suivant**.
    
18. Dans la page **Magasin de certificats**, sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat**, puis sur **Suivant** pour continuer.
    
    > [!NOTE]
    > Si la page État de la **demande de certificat en ligne** a signalé un problème avec le certificat, tel que le certificat n’est pas valide, affichez le certificat réel pour obtenir de l’aide afin de résoudre le problème. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.
  
19. Sur la page Résumé de l' **affectation du certificat** , passez en revue les informations présentées pour vérifier qu’il s’agit bien du certificat à attribuer, puis cliquez sur **suivant**.
    
20. Dans la page **Exécution de commandes**, passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez passer en revue le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer**.
    
21. Sur la page **Assistant Certificat** , vérifiez que tous les services ont une vérification verte pour indiquer qu’un certificat a été affecté, y compris OAuthTokenIssuer, comme illustré dans la figure, puis cliquez sur **Fermer**.
    
     ![Certificats installés et attribués correctement.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si vous effectuez l’installation dans un environnement de laboratoire et que vous venez de configurer l’autorité de certification à l’aide des services de certificats Active Directory, vous devrez redémarrer le serveur exécutant les services de certificats, ainsi que le serveur frontal avant le certificat. l’affectation peut être effectuée avec succès. 
  
    > [!TIP]
    >  Pour plus d’informations sur les certificats dans les services de certificats Active Directory, consultez la rubrique [Active Directory Certificate Services](https://technet.microsoft.com/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Étape 4 : démarrer les services

1. Passez en revue les conditions préalables pour l' **étape 4 : démarrer les services**.
    
2. S’il s’agit d’un pool frontal Enterprise Edition avec au moins trois serveurs, le fabric Windows est utilisé et vous devez utiliser l’applet de commande **Start-applet cspool** . Si un seul serveur est utilisé, ce qui est toujours le cas avec Standard Edition, vous pouvez utiliser la cmdlet **Start-CsWindowsService** . Dans cet exemple, nous utilisons Enterprise Edition avec trois serveurs frontaux dans le pool, ouvrez **Skype for Business Server Management Shell** et exécutez l’applet de commande **Start-applet cspool** comme illustré dans la figure. Pour tous les autres rôles, y compris le serveur Standard Edition, vous devez utiliser **Start-CsWindowsService**. Pour déployer des rôles autres que le rôle frontal, reportez-vous à la documentation de ces rôles particuliers.
    
     ![Démarrez les services Skype entreprise.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Sur la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > La commande permettant de démarrer les services sur le serveur est la méthode recommandée pour signaler que les services ont été démarrés. Cependant, il est possible qu’elle n’indique pas l’état actuel du service. Nous vous recommandons d’utiliser l’étape **État du service (facultatif)** pour ouvrir la console MMC (Microsoft Management Console) et de confirmer que les services ont démarré correctement, comme illustré dans la figure. Si un service Skype entreprise Server n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la console MMC, puis cliquer sur **Démarrer**. 
  
     ![Vérifiez que les services ont démarré.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

