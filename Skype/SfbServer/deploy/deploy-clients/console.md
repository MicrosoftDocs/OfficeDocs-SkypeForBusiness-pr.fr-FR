---
title: Configurer une console Microsoft équipes salles
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit comment configurer la console de salles d’équipes Microsoft et des périphériques.
ms.openlocfilehash: fc1d50ffe6dd7415848e02571eab1484bd3dfe22
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012612"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurer une console Microsoft équipes salles

Cet article décrit comment configurer la console de salles d’équipes Microsoft et des périphériques.
  
Vous devez uniquement effectuer ces étapes si la Skype nécessaire pour les comptes d’entreprise et Exchange ont déjà créé et testé comme décrit dans les [Salles d’équipes Microsoft de déployer](room-systems-v2.md). Vous devez le matériel et les logiciels décrits dans les [salles d’équipes Microsoft requise](../../plan-your-deployment/clients-and-devices/requirements.md). Cette rubrique contient les sections suivantes :
  
- [Préparer le support d’installation](console.md#Prep_Media)
- [Installer un certificat d’autorité de certification privé sur la console](console.md#Certs)
- [Installer Windows 10 et l’application de console Microsoft équipes salles](console.md#Reimage)
- [Configurer initiale de la console](console.md#Initial)
- [Liste de vérification du déploiement Microsoft équipes salles](console.md#Checklist)

> [!NOTE]
> Salles d’équipes Microsoft fonctionne uniquement dans un Skype pour un environnement d’entreprise où les comptes de périphériques sont correctement configurés comme décrit dans les [Salles d’équipes Microsoft déployer](room-systems-v2.md)correctement configurée.
  
## <a name="prepare-the-installation-media"></a>Préparer le support d’installation
<a name="Prep_Media"> </a>

Installation de l’application de console Microsoft équipes salles requiert un périphérique de stockage USB avec au moins 32 Go de la capacité. Il ne doit y avoir aucun autre fichier sur le périphérique ; les fichiers existants sur le stockage USB seront perdues.
  
> [!NOTE]
> Impossible de créer votre support d’installation Microsoft équipes salles en fonction de ces instructions aura un comportement inattendu.

> [!NOTE]
> La procédure ci-dessous est pour la création du support d’installation vers de nouveaux périphériques de salles d’équipes Microsoft image. Périphériques existants, par défaut, mettre à jour automatiquement à partir de Windows Update et Windows Store.
  
1. Télécharger le [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.
3. Suivez les instructions du script pour créer un disque d’installation de Microsoft équipes salles USB.

> [!CAUTION]
> Le nom du dossier dans lequel vous exécutez le support de script de création de ne peut pas contenir un espace. S’il existe un espace de nom de dossier, le script échouera.

Le script CreateSrsMedia.ps1 automatise les tâches suivantes :

1. Téléchargez le programme d’installation MSI le plus récent pour les salles d’équipes Microsoft.
2. Déterminer la version de Windows que l’utilisateur doit fournir. Les versions la plus récentes peuvent ou ne peut pas être testées et pris en charge pour une utilisation avec des périphériques Microsoft équipes salles.
3. Télécharger les composants de prise en charge nécessaires.
4. Assembler les composants nécessaires sur le support d’installation.

Une version spécifique de Windows 10 est requise, et cette version est uniquement disponible pour les clients de licence en volume.  Vous pouvez obtenir une copie à partir du [Centre de gestion des licences en Volume](https://www.microsoft.com/Licensing/servicecenter/).

Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [10 de Windows Installer et les salles d’équipes Microsoft console application](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installer Windows 10 et l’application de console Microsoft équipes salles
<a name="Reimage"> </a>

Vous devez maintenant appliquer le support d’installation que vous avez créé. Le périphérique cible s’exécute en tant qu’un matériel et l’utilisateur par défaut sera définie ne s’exécute l’application de console Microsoft équipes salles.

1. Si l’équipement est installé dans une station d’accueil (par exemple, une Surface Pro), le déconnecter de la station d’accueil.

2. Vérifiez que le périphérique cible n’est pas connecté au réseau.

3. Vérifiez que l’équipement est connecté au secteur.

4. Branchez votre disque d’installation USB sur le périphérique cible.

5. Démarrez le disque d’installation USB. Reportez-vous aux instructions de fabricant. Si votre périphérique cible est une Surface Pro, procédez comme suit pour démarrer sur le disque d’installation USB :

    a. Appuyez sur et maintenez le volume vers le bas du bouton (-).

    b. Appuyez puis relâchez le bouton d’alimentation.

    c. Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).

8. Le système s’arrêtera une fois l’installation terminée.
    
Une fois que le système est arrêté, il est recommandé supprimer le disque du programme d’installation USB. À ce stade, vous pourrez placer le périphérique cible dans sa station d’accueil (si vous utilisez un produit basé sur une station d’accueil), attacher les périphériques nécessaires pour votre salle de réunion et connexion au réseau. Reportez-vous aux instructions de fabricant.
  
### <a name="selecting-a-language"></a>Sélection d’une langue 

Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de la langue implicite ne fournit pas l’utilisateur dont la langue de l’application réelle qu’ils souhaitent (par exemple, qu’ils souhaitent l’application de console pour élaborer en Français, mais elle suit en anglais).
  
> [!NOTE]
> Les instructions suivantes s’appliquent uniquement pour les consoles créées à l’aide de la mise à jour du créateur de Windows. Systèmes hérité/dans-marché qui n’ont pas été définies à l’aide des supports avec le nouveau système de mise en service ne sera pas en mesure d’utiliser ces instructions, mais doit également préférable de l’émission initiale qui nécessite une intervention manuelle cette (Édition anniversaire vous permettent de choisir votre langue de l’application explicitement dans le cadre du programme d’installation).
  
### <a name="to-apply-your-desired-language"></a>Pour appliquer la langue de votre choix

1. Passez en mode Administrateur.
    
2. Sélectionnez le menu Démarrer.
    
3. Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .
    
4. Sélectionnez **temps &amp; langue**.
    
5. Sélectionnez **région &amp; langue**.
    
6. Sélectionnez **Ajouter une langue**.
    
7. Sélectionnez la langue que vous souhaitez ajouter.
    
8. Sélectionnez la langue que vous venez d’ajouter à la liste « Langues ».
    
9. Sélectionnez **Définir par défaut**.
    
10. Pour supprimer une langue :
    
    a. Sélectionnez la langue que vous souhaitez supprimer.
    
    b. Sélectionnez **Supprimer**.
    
11. Lancez une invite de commande avec élévation de privilèges.
    
12. Exécutez la commande suivante : 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Redémarrez le système.
    
Langage de votre choix est désormais appliqué à la console de salles d’équipes Microsoft.
## <a name="initial-set-up-of-the-console"></a>Configurer initiale de la console
<a name="Initial"> </a>

Une fois que Windows est installé, l’application de console Microsoft équipes salles prendra son processus d’installation initial lors du démarrage suivant ou si l’option /reboot a été sélectionnée.
  
1. L’écran Compte d’utilisateur apparaît. Entrez le Skype adresse de connexion (au format user@domain) du compte à utiliser avec la console de salle.
    
2. Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.
    
3. Sous « Configurer le domaine », définir le nom de domaine complet de le Skype pour Business Server. Si le Skype pour le domaine SIP de l’entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.
    
4. Cliquez sur **Suivant**.
    
5. Sélectionnez les périphériques indiqués dans l’écran de fonctionnalités, cliquez sur **suivant**. Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés. Les appareils à sélectionner sont les suivants :
    
   - Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.
    
   - Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences.  
    
   - Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.
    
     Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.
    
6. Cliquez sur **Terminer**.
    
L’application de console Microsoft équipes salles doit démarrer immédiatement la connexion à Skype pour Business Server avec les informations d’identification ci-dessus et doit également synchroniseront son calendrier avec Exchange à l’aide de ces mêmes informations d’identification. Pour plus d’informations sur l’utilisation de l’application de console, reportez-vous à l' [aide de salles d’équipes Microsoft](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salles d’équipes Microsoft s’appuie sur la présence de matériel certifié console. Même une image correctement créée contenant l’application de console Microsoft équipes salles ne démarre pas au-delà de la procédure d’installation initiale, sauf si le matériel de console est détecté. Pour des solutions Surface Pro en fonction de la Surface Pro doit être connecté à son matériel ancrer accompagnement pour passer cette vérification.
  
> [!NOTE]
> Certains utilisateurs non anglaises peut-être un clavier physique connecté à la console pendant l’installation initiale, dans le cas où les symboles ne sont pas pris en charge sur le clavier tactile.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installer un certificat d’autorité de certification privé sur la console
<a name="Certs"> </a>

La console Microsoft équipes salles doit approuver les certificats utilisés par le Skype pour professionnels et les serveurs Exchange à que se connecte. Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10. Dans un cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat dans la console Microsoft équipes salles de deux manières :
  
- Vous pouvez participer à la console à Active Directory et qui ajoute automatiquement les certificats requis donnés de l’autorité de certification est publié dans Active Directory (option de déploiement normal).
    
- Vous pouvez installer le certificat manuellement après le processus de création d’image. Avant de le faire, vous devez effectuer le [paramétrage Initial de la console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Pour installer manuellement le certificat 

1. Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Placez la console en mode admin (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
3. Exécutez la commande suivante :
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Participer à un domaine Active Directory (facultatif)
<a name="Certs"> </a>

Vous pouvez joindre les consoles de salles d’équipes Microsoft pour votre domaine. Consoles salles d’équipes Microsoft doivent être placés dans une unité d’organisation distincte à partir de stations de travail de votre PC, car le nombre de stratégies de station de travail n’est pas compatible avec Microsoft équipes salles. Un exemple courant sont les stratégies de mot de passe qui empêchent Microsoft équipes salles de démarrer automatiquement. Pour plus d’informations sur la gestion des paramètres de stratégie de groupe, reportez-vous à [Gérer les salles d’équipes Microsoft](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Pour participer à des salles d’équipes Microsoft à un domaine

1. Connexion à la console de l’administrateur de compte (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
2. Lancez l’invite de commande Powershell avec élévation de privilèges.
    
3. Saisissez la commande suivante dans Powershell :
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Par exemple, si votre nom de domaine complet est Redmond.corp.Microsoft.com et que vous souhaitez que vos consoles salles d’équipes Microsoft dans une unité d’organisation « Salles d’équipes Microsoft » qui est un enfant d’une unité d’organisation « ressources », la commande sera :
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si vous souhaitez renommer l’ordinateur lors de l’intégration à un domaine, utilisez l’indicateur - NewName suivi d’un nouveau nom de l’ordinateur.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Liste de vérification du déploiement Microsoft équipes salles
<a name="Checklist"> </a>

Utilisez la liste de vérification suivante tout en effectuant une vérification finale que la console et tous les périphériques sont configurées :
  
**Paramètres de l’application**

|||
|:-----|:-----|
|☐  <br/> |Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.  <br/> |
|☐  <br/> |Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).  <br/> |
|☐  <br/> |Le mot de passe du compte de l’administrateur est défini et vérifié.  <br/> |
|☐  <br/> |Toutes les mises à jour ont été appliquées.  <br/> |
   
**Périphériques audio/vidéo**

|||
|:-----|:-----|
|☐  <br/> |La version du microprogramme de la caméra est correcte (le cas échéant).  <br/> |
|☐  <br/> |Caméra fonctionnel et positionné de manière optimale  <br/> |
|☐  <br/> |Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.  <br/> |
|☐  <br/> |Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.  <br/> |
|☐  <br/> |La version du microprogramme du périphérique audio est correcte (le cas échéant).  <br/> |
|☐  <br/> |Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.  <br/> |
|☐  <br/> |Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.  <br/> |
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |Les câbles sont sécurisés et ne sont pas pincés.  <br/> |
|☐  <br/> |La réception audio via HDMI est fonctionnelle.  <br/> |
|☐  <br/> |La réception vidéo via HDMI est fonctionnelle.  <br/> |
|☐  <br/> |Le dock peut pivoter librement.  <br/> |
|☐  <br/> |La luminosité de l’affichage est acceptable pour l’environnement.  <br/> |
   
## <a name="see-also"></a>Voir aussi
<a name="Checklist"> </a>

[Planifier des équipes Microsoft salles](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déployer les équipes Microsoft salles](room-systems-v2.md)
  
[Configurer une console Microsoft équipes salles](console.md)
  
[Gérer les équipes Microsoft salles](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)