---
title: Facilité de gestion et outils Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
ms.openlocfilehash: 74c484b321312fc77c7a1e892f41bdeac8af49ff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768857"
---
# <a name="skype-room-system-manageability-and-tools"></a>Facilité de gestion et outils Skype Room System
 
Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
  
## <a name="administrative-portal"></a>Portail d’administration

Pour les déploiements sur site de Skype entreprise Server, vous pouvez utiliser le portail d’administration du système de salle Skype pour gérer et surveiller activement les déploiements de systèmes de salle Skype au sein de votre organisation.
  
Pour plus d’informations, consultez l’article suivant :
  
- [Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Liste de vérification Exchange

- Vérifiez qu’Autodiscover est configuré et qu’un DNS A/CNAME RECORD interne est disponible pour autodiscover.domain.com.
    
- Ping Autodiscover (par ex., ping Autodiscover.contoso.com).
    
- Testez votre service Autodiscover avec l’outil d’analyse de connectivité de Microsoft. Choisissez le premier test « je ne peux pas me connecter à Office Outlook ».
    
- Si la salle de réunion possède déjà une boîte aux lettres de ressources, développez ce compte pour le système de salle Skype (exemple de script en bas de la page).
    
## <a name="skype-for-business-checklist"></a>Liste de vérification Skype entreprise

- Exécutez les outils suivants :
    
  - Analyseur de meilleures pratiques Skype entreprise     
  - Outil d’analyse de l’intégrité de Skype entreprise (Excel)    
  - Analyseur de connectivité Skype entreprise 32 bits ou 64 bits
    
- Consultez les [nouveaux outils d’analyse et de dépannage utiles pour Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Vérifiez que vous disposez d’un pool Skype entreprise et d’un serveur Office Web Apps et que vous pouvez partager une présentation PowerPoint à l’aide du client Skype entreprise.
    
- Si la salle de réunion possède déjà une boîte aux lettres de ressources, activez-la pour Skype entreprise.
    
- Si nécessaire, demandez un numéro SDA (numéro de téléphone) pour Meeting Room System, et mettez à jour le champ de l’outil Active Directory.
    
## <a name="network"></a>Réseau

- Vérifiez que vous disposez d’une connexion réseau filaire pour le système de salle Skype.
    
- Consultez le Guide de planification réseau pour Skype entreprise.
    
- Demandez une analyse du réseau Skype entreprise auprès d’un partenaire Skype entreprise.
    
- Lire les données de performance capturées dans l’outil d’analyse de l’intégrité de Skype entreprise (Excel).
    
- Exécutez l’outil d’analyse réseau.
    
- Exécutez l’outil de diagnostic avant appel.
    
## <a name="skype-room-system-security"></a>Sécurité du système de salle Skype

Le système de salle Skype est un système incorporé qui peut être entièrement intégré dans un déploiement Windows, avec le modèle de sécurité Skype entreprise, la gestion des droits et les outils de gestion tels que SCOM. Parmi les fonctionnalités figurent :
  
- Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur 
    
- Un verrouilleur d’applications pour empêcher toute application de s’exécuter. Tous les ports USB sont désactivés en mode utilisateur.
    
  - Il n’y a pas d’applications ou d’observateurs standard dans le système de salle Skype. Tout le contenu est généré via des protocoles HTTP ou RDP.
    
  - Le PC applicatif exécute le système d’exploitation Windows Embedded Standard 7. Tout le matériel, y compris les périphériques, est fourni par les partenaires OEM.
    
  - Facultatif : rejoindre un domaine pour les Active Directory Domain Services (AD DS). La gestion locale de la sécurité et le contrôle du compte est alors possible.
    
- Vous pouvez également gérer le compte d’administrateur local à l’aide du centre d’administration Skype entreprise.
    
- Le système de salle Skype est mis à jour par le biais de processus Microsoft Update standard.
    
- Le système de salle Skype se connecte à Skype entreprise.
    
  - Skype entreprise utilise le chiffrement et l’autorisation de bout en bout pour tous les modes de communication.
    
  - Le système de salle Skype prend en charge les normes de sécurité et de conformité de Skype entreprise. Pour plus d’informations, reportez-vous à la rubrique [planification de la sécurité dans Skype entreprise Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Licence

Vérifiez que vous utilisez un KMS pour l’activation du logiciel. Si tel est le cas, vous devrez peut-être vérifier ou ajouter la clé KMS du client Skype entreprise. Si vous n’utilisez pas KMS, demandez la clé de licence en volume pour le client de MAK Skype entreprise.
  
## <a name="license-keys"></a>Clés de licence

Le système de salle Skype exécute le client de bureau Skype entreprise en arrière-plan. Si le système de salle Skype est membre du domaine, il découvre votre KMS. (et si la clé KMS du programme de licence en volume sera activée automatiquement). Le programme de licence en volume fournit également une MAK, que vous entrez pour afficher xxxxx-xxxxx-xxxxx-xxxxx. (Vous devez disposer d’un accès à Internet pour l’activer à l’aide de MAK mais pas du KMS). Pour plus d’informations, voir activation en volume d’Office 2013.
  
- Pour entrer la clé MAK, accédez à l’outil \> de gestion des licences de paramètres OEM. Cliquez sur Vérifier l’état. Lorsque l’état indique « le produit n’est pas activé », entrez la clé.
    
- Si, au cours de l’activation, vous recevez un message d’erreur indiquant que le service de gestion de licences des logiciels a signalé que la clé de produit n’est pas valide, vérifiez les éléments suivants :
    
  - Vous avez saisi la clé correctement.
    
  - Vous avez entré la clé MAK Skype entreprise et non une autre clé.
    
  - Le système a accès à Internet.
    
- Vous pouvez effectuer l’activation par téléphone, mais vous devez d’abord avoir tenté d’activer l’aide de l’outil de gestion des licences SRS. Pour effectuer l’activation par téléphone, lancez une réunion test (pas un appel de test car cela est trop court). Dans l’Assistant Activation de Microsoft Office, sélectionnez activation par téléphone, appelez Microsoft, tapez le numéro long et entrez une réponse.
    
## <a name="certificate-authority"></a>Autorité de certification

Vérifiez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 dispose d’un chemin HTTP inclus dans la propriété Liste de révocation de certificats.
  
Importez le fichier de certificat (. CRT) dans le système de salle Skype si vous utilisez Skype entreprise Server. Vous pouvez l’obtenir facilement à partir du partage CertEnroll du serveur CA, ou dans le dossier racine de confiance de n’importe quel PC lié au domaine.
  
## <a name="certificates"></a>Certificats

Vérifiez que votre autorité de certification dispose d’un chemin HTTP pour la liste de révocation de certificats. Si ce n’est pas le cas, mettez à jour votre CA pour en inclure un.
  
Dans le cadre de la procédure d’administration du système de salle Skype, \> dans le gestionnaire de certificats des paramètres système, installez les certificats. Vous aurez besoin d’une autorité de certification racine d’entreprise pour votre certificat interne.
  
Une des façons d’obtenir les certificats dont vous avez besoin est de découvrir l’autorité de certification qui a émis les certificats. Pour Skype entreprise Server, sur un PC dans Skype entreprise, cliquez sur paramètres de \> Conférence \> rendez-vous des outils de paramètres. Cette action ouvre une page Web sécurisée par l’autorité de certification qui a émis les certificats internes. Cliquez sur l’icône Verrouiller dans la barre d’adresse du navigateur pour afficher un rapport de sécurité. Cliquez sur Afficher les certificats et passez en revue la propriété Point de distribution de liste de révocation. Le deuxième paramètre CN doit être le nom de serveur de l’autorité de certification. Ouvrez l’Explorateur Windows pour cette adresse \\ \< nom \>du serveur \CertEnroll. Copiez les deux fichiers .crl et .crt sur un lecteur flash et placez-les dans la partie gauche du tableau de bord SMART.
  
Importez le fichier. CRT dans le système de salle Skype sous le dossier autorité de certification de la salle d’approbation.
  
Importez les fichiers. lrc dans le système de salle Skype dans le dossier autorités de certification intermédiaires. (Vous devez remplacer le filtre d’extension de fichier dans le gestionnaire de certificats par. crl pour voir les fichiers).
  
Remarque : le serveur Office Web Apps 2013 risque de partager la même autorité de certification que Skype entreprise. Si ce n’est pas le cas, vous ne serez pas en mesure de partager PowerPoint lors d’une réunion. Vérifiez auprès de votre service informatique et obtenez les fichiers CRT et CRL à partir du CertEnroll partage réseau de l’autorité de certification, comme expliqué ci-dessus. 
  
L’appartenance aux domaines peut simplifier certains éléments, car vous pouvez considérer le système de salle Skype comme un système Windows et il peut s’appuyer sur Active Directory pour certains aspects du certificat. Toutefois, il est préférable de gérer cela manuellement.
  

