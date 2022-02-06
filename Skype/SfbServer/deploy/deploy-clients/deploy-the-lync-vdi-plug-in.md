---
title: Déployer le plug-in Lync VDI avec Skype Entreprise Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation Skype Entreprise lors de la connexion à un bureau virtuel distant.
---

# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Déployer le plug-in Lync VDI avec Skype Entreprise Server
 
Cette rubrique décrit les procédures de déploiement pour l’utilisation Skype Entreprise lors de la connexion à un bureau virtuel distant. Les considérations de planification sont à [prendre en compte dans la Skype Entreprise dans les environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines organisations où les problèmes de sécurité et de conformité sont particulièrement sensibles. Leurs utilisateurs sont sur des ordinateurs Windows locaux et utilisent des clients sur un bureau virtuel. L Skype Entreprise sur une connexion de ce genre nécessite un logiciel de plug-in VDI supplémentaire.
  
Deux solutions sont disponibles pour le composant de plug-in VDI : une proposée par Microsoft et une autre proposée par Citrix. Microsoft recommande d’utiliser la nouvelle solution HDX RealTime Optimization Pack dans les nouveaux déploiements, mais continuera à prendre en charge le plug-in Lync VDI d’origine pour le restant de son cycle de vie. 
  
Cette rubrique fournit des détails sur le déploiement du plug-in Microsoft Lync VDI, qui est uniquement pris en charge sur Windows 7 et Windows 8 ou Windows Server 2008, et prend uniquement en charge les clients Lync 2013 ou Skype Entreprise. Il n’est pas prévu de mettre à jour ce plug-in, mais le pack d’optimisation [Citrix HDX RealTime](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype Entreprise sera mis à jour selon les besoins.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Préparer votre environnement pour le plug-in Lync VDI
<a name="Prepare_vdi"> </a>

1. Dans Skype Entreprise Server, assurez-vous que EnableMediaRedirection est définie sur TRUE pour tous les utilisateurs du plug-in Lync VDI. Pour plus d’informations, voir les rubriques d’aide pour l';cmdlet [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) et la cmdlet [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) .)
    
2. Sur le serveur du centre de données, installez le client Skype Entreprise sur tous les ordinateurs de bureau virtuels.
    
3. Sur les ordinateurs locaux, installez le plug-in Lync VDI.
    
    Les utilisateurs doivent maintenant connecter un appareil tel qu’un casque ou une webcam à leur ordinateur local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurer les paramètres de connexion Bureau à distance
<a name="Prepare_vdi"> </a>

Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, suivez les étapes suivantes sur l’ordinateur local :
  
1. Si l’ordinateur local est en cours d Windows 8, ignorez cette étape. Si l’ordinateur local exécute Windows 7 avec SP1, installez la dernière version Windows 8 du [client des services Bureau à distance](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients).
    
2. Démarrez le client Services Bureau à distance en cliquant sur **Démarrer**, puis sur **Connexion Bureau à distance**.
    
3. Cliquez sur **Options**.
    
4. Cliquez sur **l’onglet Ressources** locales. Sous **Audio distant**, cliquez **Paramètres**, puis faites les choses suivantes :
    
   - Sous **Lecture audio à distance**, **sélectionnez Lire sur cet ordinateur**.
    
   - Sous **Enregistrement audio à distance**, **sélectionnez Ne pas enregistrer**.
    
   - Cliquez sur **OK**.
    
5. Cliquez sur **l’onglet** Expérience. Sous **Performances**, videz la case de mise en **cache des bitmaps** persistantes.
    
6. Cliquez sur **l’onglet** Général. Dans **Ordinateur**, tapez le nom du bureau virtuel, puis cliquez **sur Connecter**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Connectez-vous et utilisez Skype Entreprise sur le bureau virtuel
<a name="SfB_signin"> </a>

Une fois le plug-in Lync VDI activé, l’utilisateur suit ces étapes lors de la Skype Entreprise sur le bureau virtuel.
  
1. L’utilisateur tape ses informations d’identification dans le client Skype Entreprise’exécution sur le bureau virtuel.
    
2. Une fois Skype Entreprise le plug-in Lync VDI, Skype Entreprise invite l’utilisateur à entrer à nouveau les informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.
    
3. Skype Entreprise commence le jumelage avec le plug-in Lync VDI. Alors que cela se produit, le client affiche deux icônes dans la barre Skype Entreprise statut. L’icône en bas à gauche indique qu’aucun périphérique audio n’est disponible et que l’icône clignotante en bas à droite indique que le jumelage VDI est en cours : a. Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et le jumelage VDI réussi : b. L’utilisateur peut désormais voir sa présence sur Skype Entreprise compatibles avec les appareils connectés à l’ordinateur local, et passe et répond aux appels comme d’habitude.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Résoudre les problèmes du plug-in Lync VDI
<a name="tshoot_VDI"> </a>

Reportez-vous aux sections suivantes si vous rencontrez des problèmes après avoir installé le plug-in Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problèmes d’installation du plug-in Lync VDI

Si l’installation du plug-in Lync VDI est problématique, vérifiez les points suivants :
  
- Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.
    
- Assurez-vous que la protection en écriture est désactivée. Reportez-vous à la documentation du fabricant de votre appareil pour obtenir des instructions.
    
### <a name="troubleshooting-issues-with-pairing"></a>Résolution des problèmes liés au jumelage

En cas d’échec du jumelage du plug-in Lync VDI, l’icône de jumelage en bas à droite s’affiche sous la forme d’un « X » rouge, comme illustré : 
  
Voici les raisons possibles des échecs et les actions que vous pouvez prendre pour résoudre le problème. 
  
- **L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**
    
    L’utilisateur doit se Skype Entreprise et se resserre avec les informations d’identification correctes. La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.
    
- **Une autre instance du client Bureau à distance est en cours d’exécution.**
    
    S’ils utilisent la connexion Bureau à distance dans Windows, les utilisateurs doivent :
    
1. Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr**, puis cliquez sur **Démarrer le Gestionnaire des tâches**.
    
2. Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.
    
3. Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**. 
    
4. Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter. 
    
- **Les fichiers nécessaires n’ont pas été installés correctement.**
    
    Une fois le plug-in installé sur l’ordinateur local, vérifiez que ces fichiers sont présents sous C:\Program Files\Microsoft Office\Office15 (ou la lettre de lecteur appropriée) :
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Le Skype Entreprise client est en cours d’exécution sur l’ordinateur local.**
    
    Pour utiliser le plug-in Lync VDI, un client Skype Entreprise ne doit pas être en cours d’exécution sur l’ordinateur local, sinon le jumelage échouera. En tant que meilleure pratique, l’utilisateur ne doit pas installer Skype Entreprise client sur l’ordinateur local.
    
## <a name="see-also"></a>Voir aussi
<a name="tshoot_VDI"> </a>

[Planifier les Skype Entreprise dans les environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)