---
title: Facilité de gestion et outils Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a>Facilité de gestion et outils Skype Room System
 
Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
  
## <a name="administrative-portal"></a>Portail d’administration

Pour Skype pour les déploiements sur site de serveur de l’entreprise, vous pouvez utiliser le portail d’administration système de salle Skype activement gérer et surveiller des déploiements de systèmes d’espace Skype au sein de votre organisation.
  
Pour plus d’informations, consultez les articles suivants :
  
- [Déploiement du portail d’administration Web système salle de Lync dans Lync Server 2013](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [Configuration de votre environnement de Lync Server 2013 pour le portail d’administration Web Lync salle de système](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [L’installation du portail Web d’administration de système Lync salle dans Lync Server 2013](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [À l’aide du portail Web d’administration de système Lync salle dans Lync Server 2013](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Système de chambre de Skype peuvent être surveillé via System Center Operations Manager (SCOM) par le [Pack d’administration système Skype salle](https://www.microsoft.com/en-us/download/details.aspx?id=42320) de téléchargement et de l’installer sur votre serveur SCOM. SCOM vous permet de définir des alertes, de surveiller la santé du système de salle de Skype, de générer des rapports de temps de fonctionnement et bien plus encore. Système de chambre de Skype est fourni avec un agent de surveillance préinstallé qui peut être configuré pour pointer vers le serveur SCOM. Reportez-vous au guide d’installation fourni par le fabricant de votre système de salle Skype pour savoir comment configurer l’agent de surveillance sur le système local de Skype.
  
## <a name="exchange-checklist"></a>Liste de vérification Exchange

- Vérifiez qu’Autodiscover est configuré et qu’un DNS A/CNAME RECORD interne est disponible pour autodiscover.domain.com.
    
- Ping Autodiscover (par ex., ping Autodiscover.contoso.com).
    
- Testez votre service Autodiscover avec l’outil d’analyse de connectivité de Microsoft. Choisissez le premier test, « Je n’arrive pas à se connecter avec Office Outlook ».
    
- Si la salle de réunion a déjà une boîte aux lettres de ressources, étendre ce compte pour le système de salle Skype (exemple de script en bas de la page).
    
## <a name="skype-for-business-checklist"></a>Skype pour entreprise aide-mémoire

- Exécutez les outils suivants :
    
  - Skype pour entreprise Best Practices Analyzer 
    
  - Skype pour outil d’analyse de fonctionnement entreprise (Excel) 
    
  - Skype pour Analyseur de connectivité d’entreprise 32 bits ou 64 bits
    
- Consultez [dépannage nouvelles utiles et des outils d’analyse d’Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirmer vous avez un Skype pour le pool d’entreprise et un serveur Office Web Apps et que vous pouvez partager un PowerPoint à l’aide de la Skype pour client d’entreprise.
    
- Si la salle de réunion a déjà une boîte aux lettres de ressources, l’activer pour Skype pour les entreprises.
    
- Si nécessaire, demandez un numéro SDA (numéro de téléphone) pour Meeting Room System, et mettez à jour le champ de l’outil Active Directory.
    
## <a name="network"></a>Réseau

- Assurez-vous que vous disposez d’une connexion de réseau câblé pour le système de salle de Skype.
    
- Lire le Guide de planification de Skype pour les entreprises de réseau.
    
- Demander un Skype pour l’évaluation du réseau de l’entreprise à partir d’un Skype pour le partenaire commercial.
    
- Lire les données de performance capturées dans le Skype pour outil d’analyse de fonctionnement entreprise (Excel).
    
- Exécutez l’outil d’analyse réseau.
    
- Exécutez l’outil de diagnostic avant appel.
    
## <a name="skype-room-system-security"></a>Sécurité du système local de Skype

Système de chambre de Skype est un système intégré qui peut être entièrement intégré dans un déploiement de Windows, à l’aide de la Skype pour le modèle de sécurité d’entreprise, la gestion des droits et outils de gestion de SCOM. Parmi les fonctionnalités figurent :
  
- Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur 
    
- Un verrouilleur d’applications pour empêcher toute application de s’exécuter. Tous les ports USB sont désactivés en mode utilisateur.
    
  - Aucune des applications standard ou des visionneuses ne résident sur le matériel du système de salle de Skype. Tout le contenu est généré via des protocoles HTTP ou RDP.
    
  - Le PC applicatif exécute le système d’exploitation Windows Embedded Standard 7. Tout le matériel, y compris les périphériques, est fourni par les partenaires OEM.
    
  - Facultatif : rejoindre un domaine pour les Active Directory Domain Services (AD DS). La gestion locale de la sécurité et le contrôle du compte est alors possible.
    
- Vous pouvez également gérer le compte d’administrateur local à l’aide de la Skype pour le centre d’administration Business.
    
- Système de chambre de Skype est mis à jour via des processus standard de Microsoft Update.
    
- Système de chambre de Skype se connecte avec Skype pour les entreprises.
    
  - Skype pour entreprise utilise le cryptage de bout en bout et d’autorisation pour tous les modes de communication
    
  - Système de salle Skype prend en charge Skype pour les normes de sécurité et de conformité commerciale. Voir la rubrique Planification de la sécurité dans Lync Server 2013 pour plus d’informations.
    
## <a name="license"></a>Licence

Vérifiez que vous utilisez un KMS pour l’activation du logiciel. Dans ce cas, vous devrez peut-être vérifier ou ajouter le Skype pour clé KMS de client entreprise. Si vous n’êtes pas à l’aide de KMS, puis demande la clé de licence pour le Skype pour client d’entreprise MAK en volume.
  
## <a name="license-keys"></a>Clés de licence

Système de chambre de Skype exécute le Skype pour client ordinateur de bureau d’entreprise en arrière-plan. Si le système de salle de Skype est membre d’un domaine, il découvre votre serveur gestionnaire de clés. (et si elle possède le Volume Licensing Lync clés activera automatiquement). Les licences en volume fournit également une MAK, ce qui vous permet d’entrer lorsqu’il affiche les xxxxx-xxxxx-xxxxx-xxxxx. (Vous avez besoin de l’accès Internet à activer à l’aide de la clé d’activation multiple, mais pas de KMS). Pour plus d’informations, consultez l’activation en Volume Office 2013.
  
- Pour entrer la clé MAK, accédez aux paramètres de l’OEM \> outil de gestion de licences de SRS. Cliquez sur Vérifier l’état. Lorsque le statut indique que « le produit n’est pas activé », entrez la clé.
    
- Si lors de l’activation, vous obtenez une erreur indiquant que, « « le Service de licences logicielles a signalé que la clé de produit non valide, » puis vérifiez que :
    
  - Vous avez saisi la clé correctement.
    
  - Vous avez entré le Skype pour clé MAK de l’entreprise et pas une autre clé.
    
  - Le système a accès à Internet.
    
- Vous pouvez effectuer l’activation par téléphone, mais vous devez d’abord avoir tenté d’activer l’aide de l’outil de gestion des licences SRS. Pour effectuer l’activation par téléphone, lancez une réunion test (pas un appel de test car cela est trop court). Dans l’Assistant Activation de Microsoft Office, sélectionnez l’Activation par téléphone, appelez Microsoft, tapez le numéro long et entrer une réponse.
    
## <a name="certificate-authority"></a>Autorité de certification

Vérifiez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 dispose d’un chemin HTTP inclus dans la propriété Liste de révocation de certificats.
  
Importer le fichier de certificat (.crt) sur le système de salle de Skype si pour Business Server à l’aide de Skype. Vous pouvez l’obtenir facilement à partir du partage CertEnroll du serveur CA, ou dans le dossier racine de confiance de n’importe quel PC lié au domaine.
  
## <a name="certificates"></a>Certificats

Vérifiez que votre autorité de certification dispose d’un chemin HTTP pour la liste de révocation de certificats. Si ce n’est pas le cas, mettez à jour votre CA pour en inclure un.
  
Installer des certificats dans le paramétrage de l’administration du système, espace Skype sous Paramètres du système \> Gestionnaire de certificats. Vous aurez besoin d’une autorité de certification racine d’entreprise pour votre certificat interne.
  
Une des façons d’obtenir les certificats dont vous avez besoin est de découvrir l’autorité de certification qui a émis les certificats. Pour Skype pour Business Server, sur un PC dans Skype pour entreprise, cliquez sur paramètres \> outils \> paramètres de conférence à distance. Cette opération ouvre une page web sécurisée par l’autorité de certification qui a émis les certificats Lync internes. Cliquez sur l’icône Verrouiller dans la barre d’adresse du navigateur pour afficher un rapport de sécurité. Cliquez sur Afficher les certificats et passez en revue la propriété Point de distribution de liste de révocation. Le deuxième paramètre CN doit être le nom de serveur de l’autorité de certification. Ouvrez maintenant l’Explorateur Windows pour cette adresse de \\ \< nom de serveur d’autorité de certification \>\CertEnroll. Copiez les deux fichiers .crl et .crt sur un lecteur flash et placez-les dans la partie gauche du tableau de bord SMART.
  
Importer le fichier .crt sur le système de salle de Skype sous dossier de l’autorité de Certification de salle de confiance.
  
Importez les fichiers .crl sur le système de salle Skype sous le dossier autorités de certification intermédiaires. (Vous devez modifier le filtre d’extension de fichier dans le Gestionnaire de certificats pour voir les fichiers .crl).
  
Remarque : le serveur Office Web Apps 2013 peut partager la même autorité de certification que Lync. Si ce n’est pas le cas, vous ne serez pas en mesure de partager PowerPoint lors d’une réunion. Vérifiez auprès de votre service informatique et obtenez les fichiers CRT et CRL à partir du CertEnroll partage réseau de l’autorité de certification, comme expliqué ci-dessus. 
  
L’appartenance au domaine peut simplifier certaines choses étant donné que vous pouvez traiter le système de salle Skype sous la forme d’un système Windows et il peut reposer sur Active Directory pour certains aspects du certificat. Toutefois, il est préférable de gérer cela manuellement.
  

