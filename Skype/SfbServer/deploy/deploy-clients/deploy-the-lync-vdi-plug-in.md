---
title: Déployer le plug-in Lync VDI dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype pour les entreprises lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a>Déployer le plug-in Lync VDI dans Skype Entreprise Server 2015
 
Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype pour les entreprises lors de la connexion à un bureau virtuel distant. 
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Dans ces entreprises, les utilisateurs effectuent leur travail sur des ordinateurs Windows locaux et se servent de clients sur un bureau virtuel. À l’aide de Skype pour entreprise sur une connexion qu’exige un logiciel de plug-in de VDI supplémentaire.
  
Deux solutions sont disponibles pour le composant plug-in de VDI - un offerte par Microsoft et un offertes par Citrix. Microsoft recommande l’utilisation de la nouvelle solution de Pack d’optimisation HDX en temps réel dans les nouveaux déploiements, mais continuera à prendre en charge le plug-in de VDI Lync d’origine jusqu'à la fin de son cycle de vie. 
  
Cette rubrique fournit des détails sur le déploiement de Microsoft Lync VDI plug-in, qui est pris en charge uniquement sur Windows 7 et Windows 8 ou Windows Server 2008 et ne prend en charge Lync 2013 ou Skype pour les clients d’entreprise 2015. Il n’est pas prévu de la mise à jour de ce plug-in, mais le [Pack d’optimisation Citrix HDX en temps réel](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype pour entreprise sera mis à jour en fonction des besoins.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Préparer votre environnement au plug-in Lync VDI
<a name="Prepare_vdi"> </a>

1. Dans Skype pour Business Server 2015, assurez-vous que EnableMediaRedirection a la valeur TRUE pour tous les utilisateurs du plug-in de Lync VDI. Pour plus d’informations, consultez les rubriques d’aide pour l’applet de commande [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) et l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. Sur le serveur de centre de données, installez le Skype pour client d’entreprise 2015 sur tous les postes de travail virtuels.
    
3. Sur les ordinateurs locaux, installez le plug-in Lync VDI.
    
    Les utilisateurs doivent maintenant connecter un périphérique tel qu’un casque ou une webcam à leur ordinateur local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurer les paramètres de la connexion Bureau à distance
<a name="Prepare_vdi"> </a>

Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, procédez comme suit sur l’ordinateur local :
  
1. Si l’ordinateur local exécute Windows 8, ignorez cette étape. Si l’ordinateur exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du [client des Services Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Démarrez le client des services Bureau à distance en cliquant sur **Démarrer**, puis sur **Connexion Bureau à distance **.
    
3. Cliquez sur **Options**.
    
4. Cliquez sur l’onglet **Ressources locales**. Sous **Sortie audio de l’ordinateur distant **, cliquez sur **Paramètres**, puis procédez comme suit :
    
  - Sous **Lecture audio à distance**, sélectionnez **Lire sur cet ordinateur **.
    
  - Sous **Enregistrement audio à distance**, sélectionnez **Ne pas enregistrer **.
    
  - Cliquez sur **OK**.
    
5. Cliquez sur l’onglet **Expérience**. Sous **Performance **, désactivez la case à cocher **Mise en cache permanente des bitmaps **.
    
6. Cliquez sur l’onglet **Général**. Dans **Ordinateur **, tapez le nom du bureau virtuel, puis cliquez sur **Connecter **.  
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Se connecter et utiliser Skype Entreprise sur le bureau virtuel
<a name="SfB_signin"> </a>

Une fois que le plug-in Lync VDI est activé, l’utilisateur suit ces étapes lorsque vous vous connectez à Skype pour entreprise 2015 sur le bureau virtuel.
  
1. L’utilisateur saisit ses informations d’identification dans le Skype pour client d’entreprise 2015 en cours d’exécution sur le bureau virtuel.
    
2. Une fois Skype pour entreprise 2015 détecte le plug-in Lync VDI, Skype pour entreprise 2015 invite l’utilisateur à entrer les informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.
    
3. Skype pour entreprise 2015 commence l’appariement avec le plug-in Lync VDI. Lorsque cela se produit, le client affiche deux icônes dans le Skype pour entreprise 2015 barre d’état. L’icône en bas à gauche indique qu’aucun périphérique audio n’est disponible, tandis que l’icône qui clignote en bas à droite indique que le jumelage VDI est en cours, comme indiqué :
    4. Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI :
    5. L’utilisateur peut désormais voir présence son sur Skype pour les périphériques compatibles 2015 d’entreprise qui sont connectés à l’ordinateur local et de placer et de répondent aux appels comme d’habitude.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Résolution des problèmes du plug-in Lync VDI
<a name="tshoot_VDI"> </a>

Reportez-vous aux sections suivantes si vous rencontrez des problèmes après l’installation du plug-in Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problèmes d’installation du plug-in Lync VDI 

S’il existe des problèmes avec l’installation du plug-in Lync VDI, vérifiez les points suivants :
  
- Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.
    
- Assurez-vous que la protection en écriture est désactivée. Reportez-vous à la documentation du fabricant du périphérique pour obtenir des instructions.
    
### <a name="troubleshooting-issues-with-pairing"></a>Résolution des problèmes liés au jumelage

Lorsque Lync VDI plug-in d’appariement échoue, l’icône de correspondance dans le droit inférieur s’affiche sous la forme d’un « X » rouge comme indiqué : 
  
Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier.  
  
- **L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**
    
    L’utilisateur doit se déconnecter de Skype pour les entreprises et reconnectez-vous avec les informations d’identification correctes. La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.
    
- **Une autre instance du client Bureau à distance est en cours d’exécution.**
    
    Si elles sont à l’aide de connexion Bureau à distance dans Windows, les utilisateurs doivent faire les éléments suivants :
    
1. Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr **, puis cliquez sur **Démarrer le Gestionnaire des tâches**.
    
2. Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.
    
3. Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**.  
    
4. Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter.  
    
- **Les fichiers nécessaires n’ont pas été installés correctement.**
    
    Une fois le plug-in installé sur l’ordinateur local, vérifiez que les fichiers suivants se trouvent sous C:\Program Files\Microsoft Office\Office15 (ou la lettre de lecteur qui convient) :
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Le Skype pour client d’entreprise 2015 est en cours d’exécution sur l’ordinateur local.**
    
    Pour utiliser le plug-in, qu'un Skype pour client d’entreprise 2015 ne doit pas être en cours d’exécution sur l’ordinateur local Lync VDI, sinon la correspondance échoue. Pour obtenir les meilleurs résultats, l’utilisateur n’installez pas un Skype pour entreprise 2015 client sur l’ordinateur local.
    
## <a name="see-also"></a>Voir aussi
<a name="tshoot_VDI"> </a>

#### 

[Plan de Skype pour l’entreprise dans les environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

