---
title: Gestion et outils de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lisez cette rubrique pour en savoir plus sur les outils de gestion pour Skype Room System.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093548"
---
# <a name="skype-room-system-manageability-and-tools"></a>Gestion et outils de Skype Room System
 
Lisez cette rubrique pour en savoir plus sur les outils de gestion pour Skype Room System.
  
## <a name="administrative-portal"></a>Portail d’administration

Pour les déploiements locaux de Skype Entreprise Server, vous pouvez utiliser le portail d’administration Skype Room System pour gérer et surveiller activement les déploiements de Skype Room System au sein de votre organisation.
  
Pour plus d’informations, voir l’article suivant :
  
- [Déployer le portail Web d’administration de SRS v1 dans Skype Entreprise Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Liste de vérification Exchange

- Confirmez que la découverte automatique est bien définie et qu’un enregistrement DNS A/CNAME interne est disponible pour autodiscover.domain.com.
    
- Découverte automatique ping (par exemple, ping Autodiscover.contoso.com).
    
- Testez votre service de découverte automatique à l’aide de l’outil Analyseur de connectivité Microsoft. Choisissez le premier test, « Je ne peux pas me connecter avec Office Outlook ».
    
- Si la salle de réunion dispose déjà d’une boîte aux lettres de ressources, étendez ce compte pour Skype Room System (exemple de script en bas de la page).
    
## <a name="skype-for-business-checklist"></a>Liste de vérification Skype Entreprise

- Exécutez les outils suivants :
    
  - Skype Entreprise Best Practices Analyzer     
  - Outil d’analyse de l’état de Skype Entreprise (Excel)    
  - Analyseur de connectivité Skype Entreprise 32 bits ou 64 bits
    
- Passer en revue les nouveaux outils de dépannage et [d’analyse utiles pour Office 365.](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365) Confirmez que vous avez un pool Skype Entreprise et un serveur Office Web Apps et que vous pouvez partager une présentation PowerPoint à l’aide du client Skype Entreprise.
    
- Si la salle de réunion dispose déjà d’une boîte aux lettres de ressources, activez-la pour Skype Entreprise.
    
- Si nécessaire, demandez un DID (numéro de téléphone) pour le système de salle de réunion et mettez à jour le champ Téléphone général dans l’outil Active Directory.
    
## <a name="network"></a>Réseau

- Assurez-vous que vous avez une connexion réseau câblé pour Skype Room System.
    
- Lisez le Guide de planification du réseau pour Skype Entreprise.
    
- Demandez une évaluation du réseau Skype Entreprise auprès d’un partenaire Skype Entreprise.
    
- Lisez les données de performances capturées dans l’outil d’analyse de l’état d’état de Skype Entreprise (Excel).
    
- Exécutez l’outil d’analyse réseau.
    
- Exécutez l’outil de diagnostic de pré-appel.
    
## <a name="skype-room-system-security"></a>Sécurité du système Skype Room

Skype Room System est un système incorporé qui peut être entièrement intégré dans un déploiement Windows, à l’aide du modèle de sécurité Skype Entreprise, de la gestion des droits et des outils de gestion tels que SCOM. Les fonctionnalités sont les suivantes : 
  
- Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur 
    
- Stockage d’application pour empêcher l’exécution d’applications non autorisées. Tous les ports USB sont désactivés en mode utilisateur.
    
  - Aucune application ou visionneuse standard ne réside sur le matériel Skype Room System. Tout le contenu est rendu via des protocoles HTTP ou RDP.
    
  - L’appliance PC exécute le système d’exploitation Windows Embedded Standard 7. Tout le matériel, y compris les appareils, est fourni par les partenaires OEM.
    
  - Joindre un domaine facultatif aux services de domaine Active Directory (AD DS), ce qui permet la gestion et le contrôle des comptes de sécurité locaux.
    
- Vous pouvez également gérer le compte d’administrateur local à l’aide du Centre d’administration Skype Entreprise.
    
- Skype Room System est mis à jour par le biais de processus Microsoft Update standard.
    
- Skype Room System se connecte à Skype Entreprise.
    
  - Skype Entreprise utilise le chiffrement et l’autorisation de bout en bout pour tous les modes de communication
    
  - Skype Room System prend en charge les normes de sécurité et de conformité de Skype Entreprise. Pour [plus d’informations, voir Planifier](../../plan-your-deployment/security/security.md) la sécurité dans Skype Entreprise Server.
    
## <a name="license"></a>Licence

Vérifiez que vous utilisez un service KMS pour activer le logiciel. Si c’est le cas, vous devrez peut-être vérifier ou y ajouter la clé KMS du client Skype Entreprise. Si vous n’utilisez pas kmS, demandez la clé de licence en volume pour la clé MAK du client Skype Entreprise.
  
## <a name="license-keys"></a>Clés de licence

Skype Room System exécute le client de bureau Skype Entreprise en arrière-plan. Si Skype Room System est membre du domaine, il découvrira votre kmS. (et s’il dispose de la clé KMS de licence en volume, il s’active automatiquement). Les licences en volume fournissent également une mak, que vous entrez quand elle affiche xxxxx-xxxxx-xxxxx-xxxxx. (Vous avez besoin d’un accès à Internet pour l’activer à l’aide de LA MAK, mais pas du service KMS). Pour plus d’informations, voir Activation en volume d’Office 2013.
  
- Pour entrer la clé MAK, allez à l’outil de gestion des licences \> SRS des paramètres OEM. Cliquez sur Vérifier l’état. Lorsque l’état indique « le produit n’est pas activé », entrez la clé.
    
- Si, au cours de l’activation, vous obtenez une erreur qui indique « Le service de gestion des licences logicielles a signalé que la clé de produit n’est pas valide », vérifiez que :
    
  - La clé a été entrée correctement.
    
  - Vous avez entré la clé MAK Skype Entreprise et non une autre clé.
    
  - Le système dispose d’un accès à Internet.
    
- Vous pouvez activer par téléphone, mais vous devez d’abord avoir tenté de l’activer à l’aide de l’outil de gestion des licences SRS. Pour l’activer par téléphone, démarrez une réunion de test (pas un appel de test, car c’est trop court). Dans l’Assistant Activation d’Office, sélectionnez Activation téléphonique, appelez Microsoft, tapez le numéro long et entrez une réponse.
    
## <a name="certificate-authority"></a>Autorité de certification

Confirmez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 possède un chemin d’accès HTTP inclus dans la propriété Liste de révocation de certificats.
  
Importez le fichier de certificat (.crt) dans Skype Room System si vous utilisez Skype Entreprise Server. Il est facilement obtenu à partir du partage CertEnroll du serveur ca, ou dans le dossier Racine de confiance d’un PC joint à un domaine.
  
## <a name="certificates"></a>Certificats

Vérifiez que votre autorité de certification dispose d’un chemin d’accès http pour la liste de révocation de certificats. Si ce n’est pas le cas, mettez à jour votre ca pour en inclure un.
  
Installez les certificats dans la configuration d’administration de Skype Room System sous System Settings \> Certificate Manager. Vous avez besoin de l’ac racine d’entreprise pour votre certificat interne.
  
Une façon d’obtenir les certificats dont vous avez besoin consiste à découvrir l’ac qui a émis vos certificats. Pour Skype Entreprise Server, sur un PC dans Skype Entreprise, cliquez sur Paramètres de conférence d’accès aux \> \> outils de paramètres. Cela ouvre une page web sécurisée par l’ac qui a émis les certificats internes. Cliquez sur l’icône Verrouiller dans la barre d’adresses du navigateur pour afficher un rapport de sécurité. Cliquez sur Afficher les certificats et examinez la propriété point de distribution de la CRL. Le deuxième paramètre CN doit être le nom de serveur de l’ac. Ouvrez l’Explorateur Windows pour cette \\ \< CA Server Name \> adresse \CertEnroll. Copiez les deux fichiers .crl et le fichier .crt sur un disque mémoire flash et placez-le dans le côté gauche du tableau SMART.
  
Importez le fichier .crt dans Skype Room System sous le dossier Autorité de certification des salles de confiance.
  
Importez les fichiers .crl sur Skype Room System sous le dossier Autorités de certification intermédiaires. (Vous devez modifier le filtre d’extension de fichier dans le Gestionnaire de certificats en .crl pour voir les fichiers).
  
Remarque : le serveur Office Web Apps 2013 peut partager la même cae que Skype Entreprise. Si ce n’est pas le cas, vous ne pourrez pas partager PowerPoint dans une réunion. Consultez le programme informatique et obtenez les fichiers CRT et CRL à partir du partage réseau ca CertEnroll, comme expliqué ci-dessus. 
  
L’appartenance à un domaine peut simplifier certaines choses, car vous pouvez traiter Skype Room System comme un système Windows et il peut s’appuyer sur Active Directory pour certains aspects du certificat. Toutefois, il est préférable de gérer cela manuellement.
