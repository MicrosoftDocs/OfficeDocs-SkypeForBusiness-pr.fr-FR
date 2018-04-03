---
title: Configuration d’une console Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit l’installation de la console Skype Room Systems v2 et de ses périphériques.
ms.openlocfilehash: 6e2ec8384387cefd074342abb3da316288af1f0f
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a>Configuration d’une console Skype Room Systems v2
 
Cet article décrit l’installation de la console Skype Room Systems v2 et de ses périphériques.
  
Vous devez uniquement effectuer ces étapes si le Skype nécessaire pour les comptes entreprise et Exchange ont déjà été créé et testé comme décrit dans le [déploiement de systèmes de salle Skype v2](room-systems-v2.md). Vous devez le matériel et les logiciels décrits dans les [exigences en matière de systèmes de salle Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md). Cette rubrique contient les sections suivantes :
  
- [Préparation de l’image d’installation](console.md#Prep_Image)
    
- [Installer un certificat d’autorité de certification privé sur le périphérique de tablette](console.md#Certs)
    
- [Installer Windows 10 et l’application de console de systèmes de salle Skype v2](console.md#Reimage)
   
- [Paramétrage initial de la Console](console.md#Initial)
    
- [Salle de Skype du pré-déploiement systèmes v2](console.md#Checklist)
    
> [!NOTE]
> Systèmes de salle Skype v2 ne fonctionne que dans un Skype correctement configuré pour l’environnement d’entreprise où les comptes de périphérique sont configurés correctement, comme décrit dans le [déploiement de systèmes de salle Skype v2](room-systems-v2.md). 
  
## <a name="prepare-the-installation-image"></a>Préparation de l’image d’installation
<a name="Prep_Image"> </a>

L’installation de l’application v2 de systèmes de salle Skype sur une Surface Pro ou une Surface Pro des 4 nécessite un périphérique de stockage USB avec moins de 32 Go de mémoire mis en forme comme un disque FAT32. Il ne doit y avoir aucun autre fichier sur le périphérique, les fichiers existants sur le périphérique de stockage USB seront perdues. 
  
> [!NOTE]
> Si vous ne créez pas l’image de votre console conformément à ces instructions, cela entraînera probablement un comportement inattendu. (Version 1607) mise à jour pour l’entreprise anniversaire de Windows 10 n’est plus pris en charge pour la création d’images systèmes de salle Skype v2. 
  
> [!NOTE]
> Un v2 Skype salle systèmes existants avec Windows 10 entreprise anniversaire mise à jour de déplacement vers des systèmes de salle Skype v2 mise à jour 3 par le Windows Store fonctionnera, mais une nouvelle installation doit être effectuée comme décrit ci-dessous. 
  
1. Télécharger le [package MSU pour KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).
2. Téléchargez le [script de CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
3. Placez le package MSU pour KB4056892 dans le même répertoire que le script CreateSrsMedia.ps1.
4. Exécutez le script CreateSrsMedia.ps1 à partir d’une invite de commandes avec élévation de privilèges sur un ordinateur Windows 10.


Suivez les instructions du script pour créer une disquette d’installation de systèmes de salle Skype v2 USB. Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [10 de Windows Installer et l’application de console v2 Skype salle de systèmes ](console.md#Reimage).
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>Installation de Windows 10 et de l’application de console Skype Room Systems v2 
<a name="Reimage"> </a>

Vous devrez désormais appliquer l’image que vous avez créée. Le Tablet PC s’exécute sous la forme d’une solution matérielle-logicielle, et l’utilisateur par défaut est fixé à exécuter uniquement l’application v2 de systèmes de salle de Skype. 
  
1. La tablette doit être connectée à une source d’alimentation. Commencez par l’arrêter complètement. Si nécessaire, appuyez sur le bouton d’alimentation et maintenez-le enfoncé jusqu’à ce que la tablette s’éteigne.
    
2. Connectez votre disque USB d’installation à la tablette.
    
3. Appuyez sur le bouton de diminution du volume (-) de la tablette et maintenez-le enfoncé. 
    
4. Appuyez sur le bouton d’alimentation de la tablette, puis relâchez-le.
    
5. Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).
    
6. Le système s’arrête une fois l’installation terminée.
    
Une fois que le système est arrêté, il est recommandé à retirer la disquette d’installation USB. À ce stade, vous pouvez placer la tablette dans le dock et connecter les périphériques requis pour votre salle de réunion. Reportez-vous aux instructions de fabricant.
  
 
### <a name="selecting-a-language-in-creators-update"></a>Sélection de la langue pour la mise à jour de Creator

Mise à jour de l’auteur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de la langue implicite ne fournit pas l’utilisateur avec la langue de l’application réelle qu’ils souhaitent (par exemple, ils l’application à élaborer en Français, mais il est prochaine en anglais).
  
> [!NOTE]
> Les instructions suivantes s'appliquent aux périphériques créés à l'aide de la mise à jour de Windows Creator. Les systèmes hérités/commercialisés qui n'ont pas fait correctement l'objet d'une nouvelle image pour leur nouveau système de provisionnement ne pourront pas utiliser ces instructions, mais ne requièrent pas une intervention manuelle (La version anniversaire vous permet de sélectionner la langue de l'application lors de la configuration.). 
  
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
    
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    
13. Redémarrez le système.
    
Langage de votre choix est maintenant appliqué au périphérique v2 Skype salle systèmes.
## <a name="initial-set-up-of-the-console"></a>Configuration initiale de la console 
<a name="Initial"> </a>

Une fois que Windows est installé, l’application v2 de systèmes de salle Skype iront dans son processus d’installation initial lors de son démarrage suivant ou si l’option /reboot a été choisie.
  
1. L’écran Compte d’utilisateur apparaît. Saisissez l’adresse de connexion Skype (au format utilisateur@domaine) du compte de la salle qui sera utilisé avec l’appareil.
    
2. Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.
    
3. Sous « Configurer le domaine », définissez le nom de domaine complet pour le Skype pour Business Server. Si le Skype pour le domaine SIP de l’entreprise est différent à partir du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.
    
4. Cliquez sur **Suivant**.
    
5. Sélectionnez les périphériques indiqués sur l’écran des fonctionnalités, puis cliquez sur **suivant**. Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés. Les appareils à sélectionner sont les suivants :
    
   - Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.
    
   - Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences.  
    
   - Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.
    
    Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.
    
6. Cliquez sur **Terminer**.
    
L’application doit démarrer immédiatement la connexion à Skype pour Business Server 2015 avec les informations d’identification ci-dessus et doit également commencer à synchroniser son calendrier avec Exchange à l’aide de ces mêmes informations d’identification. Pour plus d’informations sur l’utilisation de l’application, reportez-vous à l' [aide de systèmes de salle Skype version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Systèmes de salle Skype v2 s’appuie sur la présence de matériel de console certifiées (la Logitech SmartDock). Même une image correctement créée contenant l’application v2 de Skype salle systèmes chargée sur une Surface Pro des 4 ou Surface Pro ne démarre pas après la procédure d’installation initiale, sauf si le matériel de console est détecté. 
  
> [!NOTE]
> Certains utilisateurs non anglophones auront peut-être besoin d’un clavier physique connecté à la console lors de l’installation initiale. 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a>Installation d’un certificat d’une autorité de certification privée sur la tablette
<a name="Certs"> </a>

Le périphérique de v2 Skype salle systèmes doit approuver les certificats utilisés par le Skype pour l’entreprise et les serveurs Exchange à que se connecte. Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10. Dans le cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat au périphérique v2 Skype salle systèmes de deux façons :
  
- Vous pouvez connecter l’appareil à Active Directory qui ajoutera automatiquement les certificats requis, car l’autorité de certification est publiée dans Active Directory (option de déploiement ordinaire).
    
- Vous pouvez installer le certificat manuellement après le processus de création d’image. Avant cela, vous devez terminer la [configuration initiale de la console ](console.md#Initial).  
    
### <a name="to-manually-install-the-certificate"></a>Pour installer manuellement le certificat 

1. Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Placez la Surface 4 en mode administrateur (voir [gestion de dispositif et mode Admin](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).
    
3. Exécutez la commande suivante :
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a>Joindre un domaine Active Directory (facultatif)
<a name="Certs"> </a>

Vous pouvez joindre des périphériques v2 de systèmes de salle Skype à votre domaine. Périphériques de v2 Skype salle systèmes doivent être placés dans une unité d’organisation distincte à partir de vos postes de travail PC, car de nombreuses stratégies de station de travail ne sont pas compatibles avec les systèmes de salle Skype v2. Un exemple courant sont les stratégies de mot de passe qui empêchent les systèmes de salle Skype v2 de démarrer automatiquement. Pour plus d’informations sur la gestion des paramètres d’objet stratégie de groupe, reportez-vous à [Gérer les systèmes de salle Skype v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md). 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>Pour joindre Skype Room Systems v2 à un domaine

1. Connexion à la console de l’administrateur de compte (voir [gestion de dispositif et mode Admin](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).
    
2. Lancez l’invite de commande Powershell avec élévation de privilèges.
    
3. Saisissez la commande suivante dans Powershell :
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

Par exemple, si votre domaine complet est Redmond.corp.Microsoft.com et si vous souhaitez que vos périphériques v2 de systèmes de salle Skype dans une « salle de Skype systèmes v2 » unité d’organisation qui est un enfant d’une unité d’organisation « ressources », la commande sera :
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si vous souhaitez renommer l’ordinateur lors de l’intégration à un domaine, utilisez l’indicateur - NewName suivi par le nouveau nom de l’ordinateur.
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Liste de vérification du déploiement de Skype Room Systems v2
<a name="Checklist"> </a>

Utilisez la liste de vérification suivante lors de la vérification finale de la configuration complète de la console et de ses périphériques :
  
**Paramètres de l’application**

|||
|:-----|:-----|
|☐  <br/> |Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.  <br/> |
|☐  <br/> |Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).  <br/> |
|☐  <br/> |Le mot de passe du compte de l’administrateur est défini et vérifié.  <br/> |
|☐  <br/> |Toutes les mises à jour de Surface Pro 4 ou Surface Pro Systems ont été appliquées.  <br/> |
   
**Périphériques audio/vidéo**

|||
|:-----|:-----|
|☐  <br/> |La version du microprogramme de la caméra est correcte (le cas échéant).  <br/> |
|☐  <br/> |Appareil photo fonctionnel et positionnée de manière optimale  <br/> |
|☐  <br/> |Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.  <br/> |
|☐  <br/> |Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.  <br/> |
|☐  <br/> |La version du microprogramme du périphérique audio est correcte (le cas échéant).  <br/> |
|☐  <br/> |Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.  <br/> |
|☐  <br/> |Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.  <br/> |
   
**Station d’accueil**

|||
|:-----|:-----|
|☐  <br/> |Les câbles sont sécurisés et ne sont pas pincés.  <br/> |
|☐  <br/> |La réception audio via HDMI est fonctionnelle.  <br/> |
|☐  <br/> |La réception vidéo via HDMI est fonctionnelle.  <br/> |
|☐  <br/> |Le dock peut pivoter librement.  <br/> |
|☐  <br/> |La luminosité de l’affichage est acceptable pour l’environnement.  <br/> |
   
## <a name="see-also"></a>Voir aussi
<a name="Checklist"> </a>

#### 

[Plan de salle de Skype systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déployer Skype salle systèmes v2](room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](console.md)
  
[Gérer l’espace de Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

