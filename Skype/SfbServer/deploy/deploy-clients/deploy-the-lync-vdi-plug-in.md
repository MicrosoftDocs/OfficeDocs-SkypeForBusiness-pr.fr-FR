---
title: Déployer le Lync VDI plug-in avec Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype pour les entreprises lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: d939d2b269d6488de1df09e3f8aff08e2b83458e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986102"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Déployer le Lync VDI plug-in avec Skype pour Business Server
 
Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype pour les entreprises lors de la connexion à un bureau virtuel distant. Considérations de planification sont [planifier Skype pour les entreprises dans les environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Dans ces entreprises, les utilisateurs effectuent leur travail sur des ordinateurs Windows locaux et se servent de clients sur un bureau virtuel. L’utilisation de Skype pour les entreprises sur une connexion en procédant nécessite les logiciels plug-in VDI supplémentaires.
  
Il existe deux solutions disponibles pour le composant plug-in VDI - 1 proposées par Microsoft et l’autre offertes par Citrix. Microsoft recommande l’utilisation de la nouvelle solution Pack d’optimisation HDX en temps réel dans les nouveaux déploiements, mais continuera à prendre en charge le plug-in de VDI Lync d’origine pour le reste de son cycle de vie. 
  
Cette rubrique fournit des détails sur le déploiement de Microsoft Lync VDI plug-in, qui est uniquement pris en charge sur Windows 7 et Windows 8 ou Windows Server 2008 et ne prend en charge Lync 2013 ou Skype pour les clients d’entreprise. Il n’est pas prévu pour mettre à jour ce plug-in, mais le [Pack d’optimisation Citrix HDX en temps réel](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype pour les entreprises seront mis à jour selon vos besoins.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Préparer votre environnement au plug-in Lync VDI
<a name="Prepare_vdi"> </a>

1. Dans Skype pour Business Server, vérifiez que EnableMediaRedirection a la valeur True pour tous les utilisateurs de Lync VDI plug-in. Pour plus d’informations, consultez les rubriques d’aide pour l’applet de commande [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) et l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. Sur le serveur de centre de données, installez le Skype pour Business client sur tous les ordinateurs virtuels.
    
3. Sur les ordinateurs locaux, installer le plug-in Lync VDI.
    
    Les utilisateurs doivent maintenant connecter un périphérique tel qu’un casque ou une webcam à leur ordinateur local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurer les paramètres de la connexion Bureau à distance
<a name="Prepare_vdi"> </a>

Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, procédez comme suit sur l’ordinateur local :
  
1. Si l’ordinateur local exécutant Windows 8, ignorez cette étape. Si l’ordinateur local exécutant Windows 7 avec SP1, installez la dernière version de Windows 8 du [client des Services Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
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

Une fois le plug-in Lync VDI est activé, l’utilisateur procède comme suit lors de la connexion sur le bureau virtuel à Skype pour les entreprises.
  
1. L’utilisateur tape ses informations d’identification dans le Skype pour client d’entreprise en cours d’exécution sur le bureau virtuel.
    
2. Une fois Skype pour les entreprises détecte le plug-in Lync VDI, Skype pour les entreprises invite l’utilisateur à entrer de nouveau les informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.
    
3. Skype pour les entreprises commence le jumelage avec le plug-in Lync VDI. Alors que dans ce cas, le client affiche deux icônes dans le Skype pour la barre d’état Business. L’icône dans le coin inférieur gauche indique qu’aucun périphérique audio n’est disponibles et l’icône clignotant dans le coin inférieur droit indique que jumelage VDI est en cours : une. Une fois le jumelage VDI se déroule correctement, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI : b. L’utilisateur peut maintenant voir sa présence sur Skype pour les appareils compatibles métiers qui sont connectés à l’ordinateur local et passer des appels et y répondre comme d’habitude.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Résolution des problèmes du plug-in Lync VDI
<a name="tshoot_VDI"> </a>

Reportez-vous aux sections suivantes si vous rencontrez des problèmes après l’installation du plug-in Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problèmes d’installation du plug-in Lync VDI 

S’il existe des problèmes liés à l’installation du plug-in Lync VDI, vérifiez les points suivants :
  
- Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.
    
- Assurez-vous que la protection en écriture est désactivée. Reportez-vous à la documentation du fabricant du périphérique pour obtenir des instructions.
    
### <a name="troubleshooting-issues-with-pairing"></a>Résolution des problèmes liés au jumelage

Lorsque le jumelage du plug-in Lync VDI échoue, l’icône du jumelage comme un « X » rouge comme indiqué dans l’inférieur droite s’affiche : 
  
Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier.  
  
- **L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**
    
    L’utilisateur doit déconnecter Skype pour les entreprises et vous reconnecter avec les informations d’identification correctes. La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.
    
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
    
- **Le Skype pour Business client est en cours d’exécution sur l’ordinateur local.**
    
    Pour utiliser le plug-in, qu'un Skype pour le client Business ne doit pas être en cours d’exécution sur l’ordinateur local Lync VDI, sinon jumelage échouera. Meilleure pratique, l’utilisateur ne doit pas installer un Skype pour client d’entreprise sur l’ordinateur local.
    
## <a name="see-also"></a>Voir aussi
<a name="tshoot_VDI"> </a>

[Planifier Skype Entreprise dans des environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)