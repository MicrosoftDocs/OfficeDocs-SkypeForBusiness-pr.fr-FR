---
title: Déploiement du plug-in Lync VDI avec Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: 8892bf8b8772bdb301f914bca134d61e67ea934b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234402"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Déploiement du plug-in Lync VDI avec Skype entreprise Server
 
Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant. Les considérations en matière de planification s’exécutent au [plan de Skype entreprise dans les environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Dans ces entreprises, les utilisateurs effectuent leur travail sur des ordinateurs Windows locaux et se servent de clients sur un bureau virtuel. Utiliser Skype entreprise sur une connexion telle qu’un logiciel supplémentaire VDI supplémentaire est requis.
  
Il existe deux solutions disponibles pour le composant enfichable VDI, l’une proposée par Microsoft et celle proposée par Citrix. Microsoft recommande d’utiliser la nouvelle solution HDX en temps réel d’optimisation en temps réel dans de nouveaux déploiements, mais continuera à prendre en charge le plug-in Lync VDI d’origine pour le reste de son cycle de vie. 
  
Cette rubrique fournit des détails sur le déploiement du plug-in Microsoft Lync VDI qui est uniquement pris en charge sur Windows 7 et Windows 8 ou Windows Server 2008 et ne prend en charge que les clients Lync 2013 ou Skype entreprise. Il n’est pas prévu de mettre à jour ce plug-in, mais le [Pack d’optimisation en temps réel de Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype entreprise sera mis à jour selon les besoins.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Préparer votre environnement au plug-in Lync VDI
<a name="Prepare_vdi"> </a>

1. Dans Skype entreprise Server, assurez-vous que EnableMediaRedirection est défini sur TRUE pour tous les utilisateurs du plug-in Lync VDI. Pour plus d’informations, consultez les rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) et l’applet de connexion [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. Sur le serveur du centre de données, installez le client Skype entreprise sur tous les ordinateurs de bureau virtuels.
    
3. Sur l’ordinateur local, installez le plug-in Lync VDI.
    
    Les utilisateurs doivent maintenant connecter un périphérique tel qu’un casque ou une webcam à leur ordinateur local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurer les paramètres de la connexion Bureau à distance
<a name="Prepare_vdi"> </a>

Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, procédez comme suit sur l’ordinateur local:
  
1. Si l’ordinateur local exécute Windows 8, ignorez cette étape. Si l’ordinateur local exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du [client de services Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
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

Une fois que le plug-in Lync VDI est activé, l’utilisateur suit les étapes suivantes lors de la connexion à Skype entreprise sur le bureau virtuel.
  
1. L’utilisateur tape ses informations d’identification sur le client Skype entreprise exécuté sur le bureau virtuel.
    
2. Après avoir détecté le plug-in Lync VDI, Skype entreprise invite l’utilisateur à entrer de nouveau les informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.
    
3. Skype entreprise commence à jumeler avec le plug-in Lync VDI. Lorsque cela se produit, le client affiche deux icônes dans la barre d’état Skype entreprise. L’icône située dans le coin inférieur gauche indique qu’aucun périphérique audio n’est disponible et que l’icône clignotant dans le coin inférieur droit indique que le jumelage VDI est en cours: a. Après le jumelage de l’infrastructure VDI, les icônes changent pour indiquer le périphérique audio à utiliser pour les appels et le succès du jumelage d’un appareil VDI: b. L’utilisateur peut maintenant voir son statut de connexion sur les appareils compatibles Skype entreprise qui sont connectés à l’ordinateur local, et les appels et les réponses habituelles.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Résolution des problèmes du plug-in Lync VDI
<a name="tshoot_VDI"> </a>

Reportez-vous aux sections suivantes si vous rencontrez des problèmes après l’installation du plug-in Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problèmes d’installation du plug-in Lync VDI 

Si vous rencontrez des problèmes lors de l’installation du plug-in Lync VDI, vérifiez les points suivants:
  
- Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.
    
- Assurez-vous que la protection en écriture est désactivée. Pour obtenir des instructions, consultez la documentation fournie par le fabricant de votre appareil.
    
### <a name="troubleshooting-issues-with-pairing"></a>Résolution des problèmes liés au jumelage

Lorsque le jumelage du plug-in Lync VDI échoue, l’icône de jumelage dans le coin inférieur droit s’affiche sous la forme d’un «X» rouge, comme illustré ci-dessous: 
  
Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier.  
  
- **L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**
    
    Pour que l’utilisateur se déconnecte de Skype entreprise, vous devez vous reconnecter avec les informations d’identification appropriées. La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.
    
- **Une autre instance du client Bureau à distance est en cours d’exécution.**
    
    S’ils utilisent une connexion Bureau à distance dans Windows, les utilisateurs doivent procéder comme suit:
    
1. Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr **, puis cliquez sur **Démarrer le Gestionnaire des tâches**.
    
2. Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.
    
3. Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**.  
    
4. Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter.  
    
- **Les fichiers nécessaires n’ont pas été installés correctement.**
    
    Une fois le plug-in installé sur l’ordinateur local, vérifiez que les fichiers suivants se trouvent sous C:\Program Files\Microsoft Office\Office15 (ou la lettre de lecteur qui convient) :
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Le client Skype entreprise est en cours d’exécution sur l’ordinateur local.**
    
    Pour utiliser le plug-in Lync VDI, un client Skype entreprise ne doit pas être en cours d’exécution sur l’ordinateur local, sinon le jumelage échoue. En règle générale, l’utilisateur ne doit pas installer un client Skype entreprise sur l’ordinateur local.
    
## <a name="see-also"></a>Voir aussi
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
