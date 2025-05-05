def logout(self):
        """用户登出"""
        self.current_user = None
    
    def record_intake(self, amount: float, time: str, notes: str = ""):
        """记录苹果醋摄入"""
        if not self.current_user:
            return False, "请先登录"
        
        record = {
            'date': datetime.datetime.now().strftime('%Y-%m-%d'),
            'time': time,
            'amount': amount,  # 单位: 毫升
            'notes': notes
        }
