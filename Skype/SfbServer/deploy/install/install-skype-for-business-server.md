---
title: Installer Skype Entreprise Server sur les serveurs de la topologie
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: "Résumé : Découvrez comment installer les composants système Skype Entreprise Server sur chaque serveur de la topologie. Téléchargez une version d’Skype Entreprise Server gratuite à partir du Centre d’évaluation Microsoft à https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server l':."
ms.openlocfilehash: eb589b606f095deade6bd4f8921d48e1f3799cf5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864311"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installer Skype Entreprise Server sur les serveurs de la topologie
 
**Résumé :** Découvrez comment installer les composants système Skype Entreprise Server sur chaque serveur de la topologie. Téléchargez une version d’évaluation Skype Entreprise Server gratuite à partir du [Centre d’évaluation Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Une fois que la topologie est chargée dans le magasin central de gestion et qu’Active Directory sait quels serveurs rempliront les rôles, vous devez installer le système Skype Entreprise Server sur chacun des serveurs de la topologie. Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. L’installation Skype Entreprise Server système est l’étape 7 sur 8.
  
![Diagramme de vue d’ensemble.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installer Skype Entreprise Server système

Une fois que vous avez publié une topologie, vous pouvez installer les composants Skype Entreprise Server sur chaque serveur de la topologie. Cette section vous guide tout au long de l’installation de Skype Entreprise Server et de la configuration des rôles serveur pour le pool frontal et tous les rôles serveur cingliqués avec les serveurs frontux. Pour installer et configurer des rôles serveur, exécutez l’Assistant Déploiement Skype Entreprise Server sur chaque ordinateur sur lequel vous installez un rôle serveur. Vous utilisez l’Assistant Déploiement pour effectuer les quatre étapes de déploiement, y compris l’installation du magasin de configurations local, l’installation des serveurs frontaux, la configuration des certificats et le démarrage des services.
  
> [!IMPORTANT]
> Vous devez utiliser le Générateur de topologie pour terminer et publier la topologie avant de pouvoir installer Skype Entreprise Server serveurs. 
  
> [!NOTE]
> Cette procédure doit être effectuée pour tous les serveurs de la topologie. 
  
> [!CAUTION]
> Après avoir installé Skype Entreprise Server sur un serveur frontal, la première fois que vous démarrez les services, vous devez vous assurer que le service pare-feu Windows est en cours d’exécution sur le serveur. 
  
> [!CAUTION]
> Avant de suivre ces étapes, assurez-vous que vous êtes connecté au serveur avec un compte d’utilisateur de domaine à la fois administrateur local et membre du groupe RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si vous n’avez pas encore exécuté Skype Entreprise Server’installation sur ce serveur, vous serez invité à vous présenter un lecteur et un chemin d’accès pour l’installation. Cela permet d’installer un lecteur autre que le lecteur système, si votre organisation l’exige ou si vous avez des problèmes d’espace. Vous pouvez modifier le chemin d’accès de  l’emplacement d’installation Skype Entreprise Server fichiers de la boîte de dialogue Installation en un nouveau lecteur disponible. Si vous installez les fichiers d’installation sur ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Skype Entreprise Server seront également déployés à cet effet.
  
> [!IMPORTANT]
> Avant de commencer l’installation, assurez-vous que Windows Server est à jour à l’aide de Windows Update. 
  
![Windows Serveur à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installer Skype Entreprise Server système

1. Insérez le Skype Entreprise Server d’installation. Si le programme d’installation ne démarre pas automatiquement, double-cliquez sur **Installation.**
    
2. Le support d’installation nécessite Microsoft Visual C++'exécuter. Une boîte de dialogue apparaît pour vous demander si vous souhaitez l’installer. Cliquez **sur Oui.**
    
3. Examinez attentivement le contrat de licence et, si vous acceptez, sélectionnez **J’accepte** les termes du contrat de licence, puis cliquez sur **OK**. 
    
4. Smart Setup est une fonctionnalité dans Skype Entreprise Server où vous pouvez vous connecter à Internet pour vérifier les mises à jour de Microsoft Update (MU) pendant le processus d’installation, comme illustré dans la figure. Cela permet d’améliorer l’expérience en vous assurez que vous disposez des mises à jour les plus récentes pour le produit. Cliquez sur **Installer** pour commencer l’installation.
    
    > [!NOTE]
    > De nombreuses organisations ont Windows Server Update Services (WSUS) déployés dans leur environnement d’entreprise. WSUS permet aux administrateurs de gérer entièrement la distribution des mises à jour publiées via Microsoft Update sur les ordinateurs de leur réseau. Dans le cadre de la mise à jour cumulative 1, Skype Entreprise Server prise en charge de l’installation intelligente pour fonctionner avec WSUS. Les clients avec WSUS qui déploient Skype Entreprise Server pour la première fois ou qui sont mis à niveau à partir de l’environnement Lync Server 2013 à l’aide de la fonctionnalité de mise à niveau In-Place disposeront de Skype d’extraction smart setup pour les mises à jour Windows à partir de WSUS au lieu d’extraire des mises à jour de mu. Les clients souhaitant utiliser smart setup doivent exécuter smartSetupWithWSUS.psq sur tous les ordinateurs avant d’exécuter Setup.exe. 
  
     ![Capture d’écran de l’installation intelligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Dans la page Assistant Déploiement, cliquez sur Installer ou mettre **à jour Skype Entreprise Server système.**
    
6. Effectuez les procédures des procédures suivantes, lorsque vous les avez terminées, cliquez sur **Quitter** pour fermer l’Assistant Déploiement. Répétez les procédures pour chaque serveur frontal du pool.
    
### <a name="step-1-install-local-configuration-store"></a>Étape 1 : Installer le magasin de configurations local

1. Examinez les conditions préalables, puis cliquez sur **Exécuter** à côté de l’étape **1 : Installer le magasin de configurations local.**
    
    > [!NOTE]
    > Le magasin de configurations local est une copie en lecture seule du magasin central de gestion. Dans un déploiement Édition Standard, le magasin central de gestion est créé à l’aide d’une copie locale de SQL Server Express Edition sur le serveur frontal. Cela se produit lorsque vous exécutez la procédure Préparer Édition Standard serveur. Dans un déploiement Êdition Entreprise, le magasin central de gestion est créé lorsque vous publiez la topologie qui inclut un pool Êdition Entreprise frontal. 
  
2. Dans la page Installer le magasin de **configurations local,** assurez-vous que l’option Récupérer directement à partir de l’option Magasin **central** de gestion est sélectionnée, puis cliquez sur **Suivant**.
    
    SQL Server Express L’édition est installée sur le serveur local. SQL Server Express L’édition est requise pour le magasin de configurations local.
    
3. Une fois l’installation terminée, cliquez sur **Terminer**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Étape 2 : Installer ou supprimer Skype Entreprise Server composants

1. Examinez les conditions préalables, puis cliquez sur **Exécuter** à côté de l’étape 2 : Installer ou **supprimer Skype Entreprise Server composants.**
    
2. Dans la page **Configurer Skype Entreprise Server composants,** cliquez sur Suivant pour configurer les composants tels que définis dans votre topologie publiée. 
    
3. La page **Exécution de commandes** affiche un résumé des commandes et des informations d’installation au cours de la mise en place. Une fois l’affichage terminé, vous pouvez utiliser la liste pour sélectionner un journal à afficher, puis cliquer sur **Afficher le journal.**
    
4. Lorsque Skype Entreprise Server’installation des composants est terminée et que vous avez  examiné les journaux si nécessaire, cliquez sur Terminer pour effectuer cette étape dans l’installation.
    
    > [!NOTE]
    > Redémarrez le serveur si vous y êtes invité (ce qui peut se produire si Windows Expérience utilisateur de bureau devait être installée). Lorsque l’ordinateur est en cours d’exécution, vous devez exécuter à nouveau cette procédure (Étape 2 : Installer ou supprimer Skype Entreprise Server composants). 
  
    > [!NOTE]
    > Si le programme d’installation trouve des conditions préalables qui n’ont pas été satisfaites, un message « Conditions préalables non remplies » s’affiche, comme illustré dans la figure. Répondez aux conditions préalables requises, puis recommencez cette procédure (Étape 2 : Installer ou Skype Entreprise Server composants). 
  
     ![Conditions préalables requises.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vérifiez que les deux premières étapes se sont terminées comme prévu. Vérifiez qu’il existe une coche verte avec le mot **Complete**, comme illustré dans la figure.
    
     ![Les deux premières étapes de l’installation des composants sont terminées.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Exécutez **Windows update à** nouveau pour vérifier s’il existe des mises à jour après avoir installé Skype Entreprise Server Composants.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Étape 3 : Demander, installer ou affecter des certificats

1. Examinez les conditions préalables, puis cliquez sur **Exécuter** en suivant l’étape **3 : Demander, installer ou attribuer des certificats.**
    
    > [!NOTE]
    > Skype Entreprise Server inclut la prise en charge de la suite SHA-2 (SHA-2 utilise des longueurs de condensé de 224, 256, 384 ou 512 bits) de hachage digest et d’algorithmes de signature pour les connexions des clients exécutant les systèmes d’exploitation Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 ou Windows Server 2008 R2. Pour prendre en charge l’accès externe à l’aide de la suite SHA-2, le certificat externe est émis par une ca publique qui peut également émettre un certificat avec le même condensé de longueur de bits. 
  
    > [!IMPORTANT]
    > La sélection de l’algorithme de chiffrement de hachage et de signature dépend des clients et des serveurs qui utiliseront le certificat, ainsi que des autres ordinateurs et périphériques avec lesquels les clients et les serveurs communiquent, qui doivent également savoir comment utiliser les algorithmes utilisés dans le certificat. Pour plus d’informations sur les longueurs digest qui sont pris en charge dans le système d’exploitation et certaines applications clientes, voir le [blog Windows PKI - SHA2 et Windows](/archive/blogs/pki/sha2-and-windows). 
  
    Chaque Édition Standard ou serveur frontal requiert jusqu’à quatre certificats : le certificat oAuthTokenIssuer, un certificat par défaut, un certificat web interne et un certificat web externe. Toutefois, vous pouvez demander et affecter un certificat par défaut unique avec des entrées d’autres noms de sujet appropriées, ainsi que le certificat oAuthTokenIssuer. Pour plus d’informations sur les certificats requis, voir [Environmental requirements for Skype Entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype Entreprise Server [2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > La procédure suivante décrit comment configurer des certificats à partir d’une autorité de certification interne basée sur les services de certificats Active Directory. 
  
2. Dans la page **Assistant Certificat**, cliquez sur **Demander**.
    
3. Dans la page **Demande de** certificat, indiquez les données pertinentes, y compris la sélection du domaine SIP, puis cliquez sur **Suivant**.
    
4. Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification interne à votre entreprise ou publique. Vous devrez ensuite importer la réponse du certificat et lui attribuer le rôle approprié.
    
5. Dans la **page** Choisir une autorité de certification, sélectionnez l’autorité de certification Sélectionner une autorité de certification dans la liste détectée dans votre **option** d’environnement, puis sélectionnez une autorité de certification connue (via l’inscription dans les services de domaine Active Directory) dans la liste. Ou sélectionnez l’option **Spécifier une autre autorité de certification**, entrez le nom d’une autre autorité de certification dans la zone, puis cliquez sur **Suivant**.
    
6. Sur la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur d’ac.ca aura les informations requises et devra peut-être vous aider dans cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.
    
7. Sur la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur Web par défaut, cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification. 
  
8. Dans la page **Nom et sécurité Paramètres,** spécifiez **un nom convivial.** En utilisant un nom convivial, vous pouvez rapidement identifier le certificat et l’objectif. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé, ou acceptez la valeur par défaut de 2 048 bits. Sélectionnez marquer la clé privée du certificat comme exportable si vous déterminez que le certificat et la clé privée doivent être déplacés ou copiés vers **d’autres** systèmes, puis cliquez sur **Suivant**.
    
    > [!NOTE]
    > Skype Entreprise Server a des exigences minimales pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool. 
  
9. Dans la page **Informations relatives à l’entreprise**, entrez éventuellement des informations sur l’entreprise, puis cliquez sur **Suivant**.
    
10. Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.
    
11. Sur la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.
    
12. Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.
    
13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, y compris ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.
    
14. Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.
    
15. Dans la page **Exécution de commandes**, cliquez sur **Suivant**.
    
16. Dans la page **État de la demande de certificat en ligne**, passez en revue les informations affichées. Notez que le certificat a été émis et installé dans le magasin de certificats local. S’il est signalé comme ayant été émis et installé, mais qu’il n’est pas valide, assurez-vous que le certificat racine de l’ac a été installé dans le magasin de l’AC racine de confiance du serveur. Consultez la documentation de votre autorité de certification pour savoir comment extraire le certificat d’une autorité de certification racine de confiance. Si vous devez consulter le certificat extrait, cliquez sur **Afficher les détails du certificat**. Par défaut, la case à cocher Affecter le **certificat Skype Entreprise Server les utilisations des certificats** est sélectionnée. Si vous souhaitez attribuer manuellement le certificat, désactivez la case à cocher, puis cliquez sur **Terminer**.
    
17. Si vous avez effacé la case à cocher Affecter le **certificat Skype Entreprise Server utilisations** de certificats sur la page précédente, la **page** Affectation de certificat s’est présentée. Cliquez sur **Suivant**.
    
18. Dans la page **Magasin de certificats**, sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat**, puis sur **Suivant** pour continuer.
    
    > [!NOTE]
    > Si la page **État** de la demande de certificat en ligne a signalé un problème avec le certificat, par exemple si le certificat n’est pas valide, affichez le certificat réel pour obtenir de l’aide pour résoudre le problème. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.
  
19. Dans la page **Résumé de l’affectation** de certificat, examinez les informations présentées pour vous assurer qu’il s’agit du certificat à attribuer, puis cliquez sur **Suivant**.
    
20. Dans la page **Exécution de commandes**, passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez passer en revue le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer**.
    
21. Dans la **page** Assistant Certificat, vérifiez que tous les services ont une coche verte pour indiquer que tous ont reçu un certificat, y compris OAuthTokenIssuer, comme illustré dans la figure, puis cliquez sur **Fermer**.
    
     ![Certificats installés et affectés correctement.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si vous installez dans un environnement de laboratoire et que vous avez simplement installé l’autorité de certification à l’aide des services de certificats Active Directory, vous devrez redémarrer le serveur exécutant les services de certificats ainsi que le serveur frontal pour que l’affectation du certificat puisse se faire correctement. 
  
    > [!TIP]
    >  Pour plus d’informations sur les certificats dans les services de certificats Active Directory, voir [Services de certificats Active Directory.](/windows/deployment/deploy-whats-new) 
  
### <a name="step-4-start-services"></a>Étape 4 : Démarrer les services

1. Examinez les conditions préalables **pour l’étape 4 : Démarrer les services.**
    
2. S’il s’agit d’un pool frontal Êdition Entreprise avec au moins trois serveurs, Windows Fabric est utilisé et vous devez utiliser l’applet de bord **Start-CsPool.** Si un seul serveur est utilisé, ce qui est toujours le cas avec Édition Standard, vous devez utiliser l’cmdlet **Start-CsWindowsService.** Dans cet exemple, nous utilisons Êdition Entreprise avec trois serveurs frontaux dans le pool, ouvrez **Skype Entreprise Server Management Shell** et exécutez l’applet de commandes **Start-CsPool,** comme illustré dans la figure. Pour tous les autres rôles, Édition Standard serveur, vous devez utiliser **Start-CsWindowsService**. Pour déployer des rôles autres que le rôle frontal, consultez la documentation de ces rôles particuliers.
    
     ![Démarrez Skype Entreprise services.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Sur la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > La commande de démarrage des services sur le serveur est une méthode efficace pour signaler que les services ont, en fait, démarré. Cependant, il est possible qu’elle n’indique pas l’état actuel du service. Nous vous recommandons d’utiliser l’étape État du **service (facultatif)** pour ouvrir la console MMC (Microsoft Management Console) et vérifier que les services ont démarré correctement, comme illustré dans la figure. Si un Skype Entreprise Server service n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la MMC, puis cliquer sur **Démarrer.** 
  
     ![Vérifiez que les services ont démarré.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
