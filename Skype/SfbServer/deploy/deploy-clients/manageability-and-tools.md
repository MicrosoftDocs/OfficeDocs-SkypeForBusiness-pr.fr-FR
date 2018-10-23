---
title: Facilité de gestion et outils Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
ms.openlocfilehash: 9be385030ad09e73608b461c5a0c05cea70987c0
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699622"
---
# <a name="skype-room-system-manageability-and-tools"></a>Facilité de gestion et outils Skype Room System
 
Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
  
## <a name="administrative-portal"></a>Portail d’administration

Pour Skype pour les déploiements sur site Business Server, vous pouvez utiliser le portail d’administration système de salle Skype pour activement gérer et surveiller des déploiements de systèmes de salle Skype au sein de votre organisation.
  
Consultez l’article suivant pour plus d’informations :
  
- [Déployer le portail d’administration Web : v1 SRS dans Skype pour Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Système de salle Skype peuvent être surveillé par le biais de System Center Operations Manager (SCOM) en téléchargeant le [Pack d’administration système Skype salle](https://www.microsoft.com/download/details.aspx?id=42320) et de l’installer sur votre serveur SCOM. SCOM vous permet de définir des alertes, surveiller l’intégrité du système de salle Skype, générer des rapports de temps de fonctionnement et bien plus encore. Système de salle Skype est fourni avec un agent de surveillance préinstallé qui peut être configuré pour pointer vers le serveur SCOM. Consultez le guide d’installation fourni par le fabricant de votre système de salle Skype pour savoir comment configurer l’agent de surveillance sur Skype salle système.
  
## <a name="exchange-checklist"></a>Liste de vérification Exchange

- Vérifiez qu’Autodiscover est configuré et qu’un DNS A/CNAME RECORD interne est disponible pour autodiscover.domain.com.
    
- Ping Autodiscover (par ex., ping Autodiscover.contoso.com).
    
- Testez votre service Autodiscover avec l’outil d’analyse de connectivité de Microsoft. Choisissez le premier test, « Je ne parviens pas à se connecter avec Office Outlook. »
    
- Si la salle de réunion a déjà une boîte aux lettres de ressources, étendre ce compte pour le système de salle Skype (exemple de script en bas de la page).
    
## <a name="skype-for-business-checklist"></a>Skype pour la liste de vérification Business

- Exécutez les outils suivants :
    
  - Skype pour Business Best Practices Analyzer     
  - Skype pour l’outil d’analyse d’intégrité (Excel)    
  - Skype pour Business Connectivity Analyzer 32 bits ou 64 bits
    
- Consultez [Nouveaux dépannages et outils d’analyse utiles pour Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirmez avoir un Skype pour le pool d’entreprise et un serveur Office Web Apps et peuvent partager un PowerPoint à l’aide de la Skype pour client d’entreprise.
    
- Si la salle de réunion a déjà une boîte aux lettres de ressources, l’activer Skype pour les entreprises.
    
- Si nécessaire, demandez un numéro SDA (numéro de téléphone) pour Meeting Room System, et mettez à jour le champ de l’outil Active Directory.
    
## <a name="network"></a>Réseau

- Assurez-vous que vous disposez d’une connexion réseau câblé pour le système de salle Skype.
    
- Lire le Guide de planification pour Skype pour les entreprises de réseau.
    
- Demander une Skype pour l’évaluation du réseau de l’entreprise à partir d’un Skype pour un partenaire commercial.
    
- Lire les données de performances capturées dans le Skype pour l’outil d’analyse d’intégrité (Excel).
    
- Exécutez l’outil d’analyse réseau.
    
- Exécutez l’outil de diagnostic avant appel.
    
## <a name="skype-room-system-security"></a>Sécurité du système de salle de Skype

Skype salle système est un système intégré qui peut être entièrement intégré dans un déploiement de Windows, à l’aide de la Skype pour le modèle de sécurité de Business, la gestion des droits et outils de gestion de SCOM. Parmi les fonctionnalités figurent :
  
- Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur 
    
- Un verrouilleur d’applications pour empêcher toute application de s’exécuter. Tous les ports USB sont désactivés en mode utilisateur.
    
  - Aucun des applications standards ou des visionneuses ne résident sur le matériel de système de salle Skype. Tout le contenu est généré via des protocoles HTTP ou RDP.
    
  - Le PC applicatif exécute le système d’exploitation Windows Embedded Standard 7. Tout le matériel, y compris les périphériques, est fourni par les partenaires OEM.
    
  - Facultatif : rejoindre un domaine pour les Active Directory Domain Services (AD DS). La gestion locale de la sécurité et le contrôle du compte est alors possible.
    
- Vous pouvez également gérer le compte d’administrateur local à l’aide de la Skype entreprise centre d’administration.
    
- Système de salle Skype est mis à jour par le biais de processus standard de Microsoft Update.
    
- Système de salle Skype se connecte avec Skype pour les entreprises.
    
  - Skype pour les entreprises utilise le chiffrement de bout en bout et d’autorisation pour tous les modes de communication
    
  - Système de salle Skype prend en charge Skype des normes de sécurité et conformité Business. Pour plus d’informations, voir [planification de la sécurité dans Skype pour Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Licence

Vérifiez que vous utilisez un KMS pour l’activation du logiciel. Dans ce cas, vous devrez peut-être vérifier ou ajouter la Skype pour la clé d’entreprise client KMS. Si vous n’utilisez pas KMS, puis demande la clé de licence pour le Skype pour le client Business MAK multiple.
  
## <a name="license-keys"></a>Clés de licence

Skype salle système exécute la Skype pour le client de bureau d’entreprise en arrière-plan. Si le système de salle de Skype est membre du domaine, il découvre votre KMS. (et si elle a la clé KMS de gestion des licences en Volume il activera automatiquement). Gestion des licences en volume fournit également une clé MAK, que vous entrez lorsqu’il affiche les xxxxx-xxxxx-xxxxx-xxxxx. (Vous devez accès à Internet pour l’activer à l’aide de la clé d’activation multiple, mais pas KMS). Pour plus d’informations, voir activation en Volume d’Office 2013.
  
- Pour entrer la clé MAK, accédez à paramètres OEM \> outil de gestion des licences SRS. Cliquez sur Vérifier l’état. Lorsque l’état indique « produit n’est pas activé », entrez la clé.
    
- Si pendant l’activation, vous obtenez une erreur indiquant « « le Service de licences logicielles a signalé que la clé de produit est non valide, « puis vérifiez que :
    
  - Vous avez saisi la clé correctement.
    
  - Vous avez entré le Skype pour la clé MAK Business et pas une autre clé.
    
  - Le système a accès à Internet.
    
- Vous pouvez effectuer l’activation par téléphone, mais vous devez d’abord avoir tenté d’activer l’aide de l’outil de gestion des licences SRS. Pour effectuer l’activation par téléphone, lancez une réunion test (pas un appel de test car cela est trop court). Dans l’Assistant Activation Office, sélectionnez l’Activation par téléphone, appelez Microsoft, tapez le numéro de type long, entrer une réponse.
    
## <a name="certificate-authority"></a>Autorité de certification

Vérifiez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 dispose d’un chemin HTTP inclus dans la propriété Liste de révocation de certificats.
  
Importer le fichier de certificat (.crt) sur le système de salle Skype si vous utilisez Skype pour Business Server. Vous pouvez l’obtenir facilement à partir du partage CertEnroll du serveur CA, ou dans le dossier racine de confiance de n’importe quel PC lié au domaine.
  
## <a name="certificates"></a>Certificats

Vérifiez que votre autorité de certification dispose d’un chemin HTTP pour la liste de révocation de certificats. Si ce n’est pas le cas, mettez à jour votre CA pour en inclure un.
  
Installer des certificats dans les paramètres d’administration du système sous Paramètres système salle Skype \> Gestionnaire de certificats. Vous aurez besoin d’une autorité de certification racine d’entreprise pour votre certificat interne.
  
Une des façons d’obtenir les certificats dont vous avez besoin est de découvrir l’autorité de certification qui a émis les certificats. Pour Skype pour Business Server, sur un PC dans Skype pour les entreprises, cliquez sur paramètres \> outils \> paramètres de conférence rendez-vous. Une page web sécurisée par l’autorité de certification qui a émis les certificats internes s’ouvre. Cliquez sur l’icône Verrouiller dans la barre d’adresse du navigateur pour afficher un rapport de sécurité. Cliquez sur Afficher les certificats et passez en revue la propriété Point de distribution de liste de révocation. Le deuxième paramètre CN doit être le nom de serveur de l’autorité de certification. Ouvrez l’Explorateur Windows pour cette adresse maintenant \\ \< nom de serveur d’autorité de certification \>\CertEnroll. Copiez les deux fichiers .crl et .crt sur un lecteur flash et placez-les dans la partie gauche du tableau de bord SMART.
  
Importer le fichier .crt au système sous le dossier approuvé une autorité de Certification salle salle Skype.
  
Importer les fichiers .crl sur le système de salle Skype sous le dossier autorités de certification intermédiaires. (Vous devez modifier le filtre d’extension de fichier dans le Gestionnaire de certificats en .crl pour afficher les fichiers).
  
Remarque : Le serveur Office Web Apps 2013 peut-être partager la même autorité de certification en tant que Skype pour les entreprises. Si ce n’est pas le cas, vous ne serez pas en mesure de partager PowerPoint lors d’une réunion. Vérifiez auprès de votre service informatique et obtenez les fichiers CRT et CRL à partir du CertEnroll partage réseau de l’autorité de certification, comme expliqué ci-dessus. 
  
Appartenance à un domaine peut simplifier les choses étant donné que vous pouvez traiter le système de salle Skype comme un système Windows et il peut s’appuient sur Active Directory pour certains aspects du certificat. Toutefois, il est préférable de gérer cela manuellement.
  

